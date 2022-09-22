<template>
  <v-layout>
    <v-flex>
      <v-card flat color="transparent" class="my-3">
        <v-card-text
          class="white--text display-1 text-center text-wrap"
          style="word-break: normal"
          >Projects I have worked on</v-card-text
        >
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Ring Signature Scheme Web Platform</v-card-title>
        <v-card-subtitle class="white--text"
          >6.857 (Applied Cryptography) Final Project</v-card-subtitle
        >
        <v-card-text class="white--text">
          <p>
            A web platform that enables messages to be signed with cryptographic ring signatures, allowing for official endorsement while preserving anonimity. 
          </p>
          <p>
            Made with Vue (frontend), Vuetify (ui-toolkit) and Python.
          </p>
          Source code available
          <a href="https://github.com/jonabox/Web-Based-Ring-Signature-Scheme">here</a>.
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Pizza-Partner</v-card-title>
        <v-card-subtitle class="white--text"
          >MIT Web Lab Project (2020)</v-card-subtitle
        >
        <v-card-text class="white--text">
          <p>
            A website that lets students partner up with other students within
            the same dorm so that they can make a group Domino's order and can
            save money. Pizza Partner achieves this by automatically applying
            coupons to the combined order.
          </p>
          <p>
            Made with Vue (frontend), Vuetify (ui-toolkit), SQLite (database)
            Stripe.js (payments)
          </p>
          Source code available
          <a href="https://github.com/jonabox/Pizza-Partner">here</a>.
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Multi-Party Computation Web Platform </v-card-title>
        <v-card-subtitle class="white--text"
          >MIT Research Program (2019)
        </v-card-subtitle>
        <v-card-text class="white--text">
          <p>
            Web platform that allows for the multi-party computation of
            cryptographic functions
          </p>
          <p>
            Made with Vue (frontend), BootstrapVue (ui-toolkit), Let'sEncrypt
            (TLS certificates)
          </p>
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Mentorly</v-card-title>
        <v-card-subtitle class="white--text"
          >MIT 6.170 Software Studio Project (2018)</v-card-subtitle
        >
        <v-card-text class="white--text">
          <p>
            Class final project website that connects students to mentors in
            academic and professional disciplines
          </p>
          <p>
            Made with Vue (frontend), Semantic (frontend-components), SQLite
            (database)
          </p>
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>History Box</v-card-title>
        <v-card-subtitle class="white--text"
          >MIT Web Lab Project (2018)</v-card-subtitle
        >
        <v-card-text class="white--text">
          <p>
            Website that allows users to view and vote on historic, celebrated
            photos
          </p>
          <p>Made with Flask and MongoDB</p>
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
