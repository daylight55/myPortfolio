<template>
  <v-navigation-drawer
    app
    :value="value"
    @input="$emit('input', $event)"
  >
    <v-list-item>
      <v-list-item-title class="title">Links</v-list-item-title>
      <v-btn
        icon
        @click="value = false"
      >
        <v-icon>fas fa-angle-left</v-icon>
      </v-btn>
    </v-list-item>
    <v-divider />
    <v-list nav>
      <v-list-item
        v-for="menu in menus"
        :key="menu.title"
        :to="menu.url"
      >
        <v-list-item-icon>
          <v-icon>{{ menu.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ menu.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      menus: [
        { title: 'Profile', icon: 'fas fa-address-card', url: '/' },
        { title: 'Skill Set', icon: 'fas fa-cogs', url: '/topics/skillset' },
        { title: 'Career', icon: 'fas fa-road', url: '/topics/career' },
        { title: 'Works', icon: 'fas fa-archive', url: '/topics/works' },
      ],
    };
  },
  props: {
    value: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
