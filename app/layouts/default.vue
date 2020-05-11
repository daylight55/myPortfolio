<template>
  <v-app>
    <Header />
    <v-content class="mb-12 pb-6">
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <BottomBar />
  </v-app>
</template>

<script>
import Header from "~/components/Header.vue";
import BottomBar from "~/components/BottomBar.vue";

export default {
  components: {
    Header,
    BottomBar
  },
  data() {
    return {};
  }
};
</script>
