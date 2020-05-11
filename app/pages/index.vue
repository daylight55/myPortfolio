<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-avatar size="300" data-aos="fade-up" data-aos-once="true">
        <img src="@/assets/andon.jpg" />
      </v-avatar>
      <div>
        <h2>Andon</h2>
        <h3>長所</h3>
        <p>一番好きなのは</p>
        <h3>短所</h3>
        <p>一番好きなのは</p>
        <h3>趣味</h3>
        <p>なんやらかんやら</p>
      </div>
      <div>
        <v-icon>fab fa-twitter</v-icon>
        <v-icon>fab fa-github</v-icon>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      github_icon_src: require("@/assets/github.png"),
      twitter_icon_src: require("@/assets/twitter.png")
    };
  },
  props: {
    drawer: {
      type: Boolean,
      default: false
    }
  }
};
</script>
