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
        </v-card-text>
      </v-card>
      <v-img
        class="center rounded-lg"
        max-width="1000px"
        dark
        :src="require('~/assets/grad_22.jpg')"
        :lazy-src="require('~/assets/grad_22_min.jpg')"
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
