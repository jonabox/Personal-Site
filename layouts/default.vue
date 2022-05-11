<template>
  <v-app style="background: linear-gradient(45deg, #4f0042 0%, #240087 100%)">
    <v-app-bar dense app clipped-left color="rgb(0, 0, 0, 0.1)" style="backdrop-filter: blur(4px)">
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn large icon href="https://github.com/jonabox">
        <v-icon>mdi-github</v-icon>
      </v-btn>
      <v-btn large icon href="https://linkedin.com/in/jonathan-esteban-771066138/">
        <v-icon>mdi-linkedin</v-icon>
      </v-btn>
      <v-btn large icon href="mailto:jesteban@mit.edu">
        <v-icon>mdi-email</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer clipped permanent app :mini-variant="isScreenSmall" color="rgb(0, 0, 0, 0.1)">
      <v-list >
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>

        <v-list-item href="https://pizza-partner.herokuapp.com/" target="_blank">
          <v-list-item-action>
            <v-icon>mdi-food</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Pizza Partner</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer class="font-weight-light text-center text-caption" app absolute tile inset color="rgb(0, 0, 0, 0)">
    Made with Nuxt.js, powered by Netlify
    <v-spacer></v-spacer>
    <div>&copy; {{ new Date().getFullYear() }}</div>
  </v-footer>
  </v-app>
</template>

<script>
export default {
  computed: {
    isScreenSmall() {
      return this.$vuetify.breakpoint.mdAndDown;
    },
  },
  data() {
    return {
      items: [
        {
          icon: "mdi-home",
          title: "Welcome",
          to: "/",
        },
        {
          icon: "mdi-book-open-variant",
          title: "Background",
          to: "/background",
        },
        {
          icon: "mdi-hammer-wrench",
          title: "Projects",
          to: "/projects",
        },
      ],
      miniVariant: false,
      title: "Jonathan Esteban",
    };
  },
};
</script>
