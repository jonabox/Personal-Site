<template>
  <v-layout>
    <v-flex>
      <v-card flat color="transparent" class="ma-3">
        <v-card-text
          class="white--text display-1 text-center text-wrap pb-0"
          style="word-break: normal"
        >
          {{ "Featured New Releases!" }}
        </v-card-text>
        <v-card-text
          class="white--text caption text-center text-wrap"
          style="word-break: normal"
        >
          (according to Spotify's API)
        </v-card-text>
        <!-- Country Selection -->
        <v-autocomplete
          :items="countries"
          item-text="country"
          item-value="country_code"
          label="Music Market"
          v-model="selectedCountry"
          v-on:change="getReleases"
        >
          <template v-slot:item="slotProps">
            <v-icon
              :class="'mr-2 fi fi-' + slotProps.item.country_code.toLowerCase()"
            ></v-icon>
            {{ slotProps.item.country }}
          </template>
          <template v-slot:prepend>
            <v-icon :class="'fi fi-' + selectedCountry.toLowerCase()"></v-icon>
          </template>
        </v-autocomplete>
        <v-container v-if="areAlbumsLoaded" fluid>
          <v-row justify="space-around">
            <!-- Release Cards -->
            <v-card
              v-for="item of albums"
              class="my-3"
              :key="item.id"
              :max-width="profileSize"
              color="rgb(0, 0, 0, 0.3)"
            >
              <!-- Release Title -->
              <v-card-title class="pb-0">
                <div
                  style="
                    white-space: nowrap;
                    word-break: normal;
                    overflow: hidden;
                    text-overflow: ellipsis;
                  "
                  v-text="item.name"
                ></div>
              </v-card-title>
              <!-- Release Artists -->
              <v-chip-group>
                <a
                  v-for="(artist, index) in item.artists"
                  :key="artist.id"
                  :href="artist.external_urls.spotify"
                  target="_blank"
                  rel="noopener noreferrer"
                  style="text-decoration: none; color:inherit"
                >
                  <v-chip
                    v-text="artist.name"
                    label
                    outlined
                    :small="isScreenSmall"
                    :class="index == 0 ? 'ml-1 mb-2' : 'mb-2'"
                  >
                  </v-chip>
                </a>
              </v-chip-group>
              <!-- Release Image -->
              <a
                :href="item.external_urls.spotify"
                target="_blank"
                rel="noopener noreferrer"
                style="text-decoration: none"
              >
                <!-- 0th and 2nd images corresponds to 640x640 and 64x64 resolutions, respectively -->
                <v-img
                  :src="item.images[0].url"
                  :lazy-src="item.images[2].url"
                  :height="profileSize"
                  :width="profileSize"
                >
                </v-img>
              </a>
              <!-- Metadata -->
              <v-card-actions class="pb-0">
                <v-card-subtitle v-text="formatDate(item.release_date)" />
                <v-spacer />
                <v-card-subtitle v-text="item.album_type" />
              </v-card-actions>
            </v-card>
          </v-row>
        </v-container>
        <!-- Not yet loaded -->
        <v-container v-else fluid>
          <v-row justify="space-around">
            <!-- Release Cards -->
            <v-card
              v-for="n in 12"
              :key="n"
              :width="profileSize"
              class="my-3"
              color="rgb(0, 0, 0, 0.3)"
            >
              <v-skeleton-loader
                loading
                :width="profileSize"
                type="article, image"
              ></v-skeleton-loader>
            </v-card>
          </v-row>
        </v-container>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";
import axios from "axios";
import countries from "~/assets/countries.json";
import "/node_modules/flag-icons/css/flag-icons.min.css";
var querystring = require("querystring");
const DATE_FORMAT = { weekday: "long", month: "long", day: "numeric" };

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
  data() {
    return {
      areAlbumsLoaded: false,
      albums: [],
      nextURL: null,
      token: null,
      countries: require("~/assets/countries.json"),
      selectedCountry: "US",
    };
  },
  methods: {
    getReleases() {
      let data = {
        headers: {
          Authorization: "Bearer " + this.token, //the token is a variable which holds the token
        },
        params: {
          country: this.selectedCountry,
          limit: 50,
          token: this.token,
        },
      };
      axios
        .get("https://api.spotify.com/v1/browse/new-releases", data)
        .then((response) => {
          this.albums = response.data.albums.items;
          this.nextURL = response.data.albums.next;
          this.areAlbumsLoaded = true;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    loadMoreAlbums() {
      let data = {
        headers: {
          Authorization: "Bearer " + this.token, //the token is a variable which holds the token
        },
      };
      axios
        .get(this.nextURL, data)
        .then((response) => {
          this.albums = this.albums.concat(response.data.albums.items);
          // Spotify limits max number of featured releases to 100
          // this.nextURL = response.data.albums.next;
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
    getToken() {
      var client_id = "673577b735f84ce6a37c832559732ade";
      var client_secret = "cca028a0644e4615ab6ddd231ffe0d73";
      let headers = {
        headers: {
          "Content-Type": "application/x-www-form-urlencoded",
        },
      };

      let data = {
        grant_type: "client_credentials",
        redirectUri: "http://localhost:3000",
        client_id: client_id,
        client_secret: client_secret,
      };
      axios
        .post(
          "https://accounts.spotify.com/api/token",
          querystring.stringify(data),
          headers
        )
        .then((response) => {
          this.token = response.data.access_token;
          this.getReleases();
          // console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
    formatDate(date) {
      return new Date(date).toLocaleDateString("en-US", DATE_FORMAT);
    },
  },
  mounted() {
    this.getToken();
    window.onscroll = () => {
      let bottomOfWindow =
        document.documentElement.scrollTop + window.innerHeight ===
        document.documentElement.offsetHeight;

      if (bottomOfWindow && this.areAlbumsLoaded) {
        this.loadMoreAlbums();
      }
    };
  },
  computed: {
    profileSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "90vmin";
        case "sm":
          return "90vmin";
        case "md":
          return 300;
        case "lg":
          return 400;
        case "xl":
          return 400;
      }
    },
    isScreenSmall() {
      return this.$vuetify.breakpoint.mdAndDown;
    },
  },
};
</script>