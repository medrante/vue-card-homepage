<template>
  <v-main>
    <v-row justify="space-around" :key="index" v-for="(tool, index) in tools">
      <v-card :href="tool.link">
        <v-card-title>{{ tool.name }}</v-card-title>
        <v-card-text>{{ tool.description }}</v-card-text>
      </v-card>
    </v-row>
  </v-main>
</template>

<script>
export default {
  name: "Cards",
  props: {
    tools: []
  },
  methods: {
    goTo(link) {
      this.$router(link);
    }
  }
};
</script>

<style scoped></style>
