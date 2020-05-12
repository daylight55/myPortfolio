<template>
  <div>
    <h2 class="mt-6 mb-6">BLOG</h2>
    <v-divider></v-divider>
    <v-row class="mb-6" no-gutters>
      <v-col v-for="n in 3" :key="n" :cols="n === 2 ? 6 : undefined">
        <v-card class="pa-2" outlined tile>
          {{ n }} of 3 {{ n === 2 ? "(wider)" : "" }}
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {};
</script>

<style scoped></style>
