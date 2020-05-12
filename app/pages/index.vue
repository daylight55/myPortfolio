<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-avatar
        size="300"
        data-aos="fade-up"
        data-aos-once="true"
      >
        <v-img :src="icon_src" />
      </v-avatar>
      <div>
        <h2>まさ</h2>
        <h3>LINKS</h3>
        <div>
          <v-icon>fab fa-twitter</v-icon>
          <v-icon>fab fa-github</v-icon>
        </div>
        <h3>長所</h3>
        <p>一番好きなのは</p>
        <h3>短所</h3>
        <p>一番好きなのは</p>
        <h3>趣味</h3>
        <p>なんやらかんやら</p>
        <h3>自己PR</h3>
        <p></p>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      icon_src: require('@/assets/andon.jpg'),
    };
  },
  props: {
    drawer: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
