<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Veutify Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        text
        rounded
        :to="link.url"
      >{{link.label}}</v-btn>
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
          :to="link.url"
        >{{ link.label }}</v-btn>
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} —
          <strong>Vuetify Dashboard</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      showPassword: false,
      links: [{ label: "Home", url: "/" }, { label: "Login", url: "/login" }, { label: "Dashboard", url: "/dashboard" },]
    };
  }
};
</script>