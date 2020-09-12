<template>
  <v-layout>
    <v-flex>
      <v-card flat color="transparent" class="my-4">
        <v-card-text class="display-4 text-center" style="word-break: normal">Welcome to my site!</v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-img dark :src="require('~/assets/iceland.jpeg')"></v-img>
        <v-card-text>
          <p class="display-2 text-center">I am a Puerto Rican Master's Student at MIT. I hope to graduate by May 2021 and will be looking for full-time positions in the meantime. Exciting!!!</p>
        </v-card-text>
      </v-card>

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