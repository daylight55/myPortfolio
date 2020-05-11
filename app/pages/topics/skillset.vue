<template>
  <div>
    <v-tabs color="grey darken-4" v-model="tab">
      <v-tabs-slider color="grey" />
      <v-tab v-for="item in tab_items" :key="item.link" :href="`#${item.link}`">
        {{ item.link_name }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item v-for="(contents, i) in front_contents" :key="`fc_${i}`">
        <v-card flat>
          <v-card-text>{{ contents.topic }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: null,
      tab_items: [
        { link: "frontend", link_name: "FRONT" },
        { link: "backend", link_name: "BACK" },
        { link: "infrastructure", link_name: "INFRA" }
      ],
      front_contents: [
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" }
      ],
      back_contents: [
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" }
      ],
      infra_contents: [
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" },
        { topic: "Javascript", point: "3", detail: "初級程度" }
      ]
    };
  }
};
</script>

<style scoped>
.v-tabs {
  width: 100%;
  height: 100%;
}

.v-window {
  height: calc(100% - 48px); /* タブ領域の高さを引く */
}

.v-tab__items,
.v-window-item,
.v-window >>> div.v-window__container {
  /* ここが重要 */
  height: 100%;
}
</style>
