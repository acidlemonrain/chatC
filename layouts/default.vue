<template>
  <v-app light>
    <v-toolbar :clipped-left="clipped" fixed app flat>
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-btn icon :to="'/'" large>
        <v-icon>home</v-icon>
      </v-btn>

      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn outline v-on="on">Dropdown</v-btn>
        </template>

        <v-card flat>
          <v-layout column>
            <v-btn flat :to="'/login'">Link One</v-btn>
            <v-btn flat :to="'/home'">Link Two</v-btn>
            <v-btn flat :to="'/zone'">Zone</v-btn>
          </v-layout>
        </v-card>
      </v-menu>
    </v-toolbar>

    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "apps",
          title: "Welcome",
          to: "/"
        },
        {
          icon: "bubble_chart",
          title: "Inspire",
          to: "/inspire"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>
<style scoped>
.custom-appear-class {
  opacity: 0;
}
</style>

