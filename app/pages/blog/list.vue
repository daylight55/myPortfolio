<template>
  <div>
    <h2 class="mt-6 mb-6">BLOG</h2>
    <v-divider></v-divider>

    <v-row
      class="mb-6"
      no-gutters
    >
      <v-col
        v-for="(post,i) in posts"
        :key="i"
        :cols="4"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
          <v-card-title>{{ post.title }}</v-card-title>
          <v-img :src="illust_path"></v-img>
          <v-card-subtitle>{{ post.contents }}</v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
    <v-btn to="/blog/upload">
      <span>ログイン(※管理者用です)</span>
      <v-icon>fas fa-sign-in-alt</v-icon>
    </v-btn>
  </div>
</template>

<script>
export default {
  data() {
    return {
      illust_path: require('@/assets/blog/fight.png'),
      posts: [
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。...........',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
        {
          title: 'CKE動かしてみた',
          contents: 'まずgitからソースを取得します。',
        },
      ],
    };
  },
};
</script>

<style scoped></style>
