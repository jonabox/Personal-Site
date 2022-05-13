<template>
  <v-layout >
    <v-flex>
      <v-card flat color="transparent" class="my-4">
        <v-card-text class="display-2 text-center text-wrap white--text">Welcome to my site!</v-card-text>
      </v-card>
      <v-card flat color="transparent" class="my-3">
        <v-card-text>
          <p
            class="headline text-center text-wrap white--text"
          >I am a Puerto Rican Master's alumnus at MIT. I graduated in February 2022 and am currently looking for full-time positions. Exciting!!!</p>
        </v-card-text>
      </v-card>
      <v-img class="center rounded-lg" max-width="1000px" dark :src="require('~/assets/marina.jpg')" :lazy-src="require('~/assets/marina-min.jpg')"></v-img>
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
  border-radius:10px;
}
</style>
