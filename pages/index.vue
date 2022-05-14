<template>
  <v-layout>
    <v-flex>
      <v-card flat color="transparent" class="my-4">
        <v-card-text class="display-2 text-center text-wrap white--text"
          >Hi, welcome to my site!
        </v-card-text>
      </v-card>
      <v-card flat color="transparent" class="my-3">
        <v-card-text>
          <p class="headline text-center text-wrap white--text">
            I am a Puerto Rican Software Engineer interested in all things
            software development, web design, and cyber-security.
          </p>
          <p class="subtitle-1 text-center text-wrap white--text">
            I recently graduated from my Master's program at MIT in February
            2022 and am currently looking for full-time positions. Exciting!!!
          </p>
        </v-card-text>
      </v-card>
      <v-img
        class="center rounded-lg"
        max-width="1000px"
        dark
        :src="require('~/assets/marina.jpg')"
        :lazy-src="require('~/assets/marina-min.jpg')"
        ><template v-slot:placeholder>
          <v-row class="fill-height ma-0" align="center" justify="center">
            <v-progress-circular
              indeterminate
              color="grey lighten-5"
            ></v-progress-circular>
          </v-row> </template
      ></v-img>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
};
</script>

<style scoped>
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  border-radius: 10px;
}
</style>
