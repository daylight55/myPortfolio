<template>
  <v-card>
    <v-app-bar
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <NavigationDrawer v-model="drawer" />
  </v-card>
</template>

<script>
import NavigationDrawer from '~/components/NavigationDrawer.vue';

export default {
  components: {
    NavigationDrawer,
  },
  data() {
    return {
      drawer: false,
      title: "Andon's Portfolio",
    };
  },
};
</script>
