<template>
  <v-layout>
    <v-flex>
      <v-card outlined color="rgb(0, 0, 0, 0.1)" class="my-3">
                <v-card-text class="display-3 font-weight-thin text-center" style="word-break: normal">404: nothing to see here!</v-card-text>
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
    VuetifyLogo
  }
};
</script>