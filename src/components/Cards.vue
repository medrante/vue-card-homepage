<template>
  <v-main>
    <v-item-group>
      <v-container>
        <v-layout row wrap>
          <v-flex xs12 sm6 md4 lg3 v-for="(tool, index) in tools" :key="index">
            <v-card :href="tool.link" class="text-xs-center ma-3">
              <v-card-title>{{ tool.name }}</v-card-title>
              <v-card-text>{{ tool.description }}</v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-item-group>
  </v-main>
</template>

<script>
export default {
  name: "Cards",
  props: {
    tools: Array
  },
  methods: {
    goTo(link) {
      this.$router(link);
    }
  }
};
</script>

<style scoped></style>
