<template>
  <v-bottom-navigation
    fixed
    grow
    mandatory
    color="purple lighten-1"
  >
    <v-btn
      v-for="menu in menus"
      :key="menu.title"
      :to="menu.url"
    >
      <span>{{ menu.title }}</span>
      <v-icon>{{ menu.icon }}</v-icon>
    </v-btn>
  </v-bottom-navigation>
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
};
</script>

<style scoped></style>
