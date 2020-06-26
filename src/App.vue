<template>
  <v-app>
    <AppNavigation />
    <Cards :tools="tools" />
  </v-app>
</template>

<script>
import AppNavigation from "./components/AppNavigation";
import Cards from "./components/Cards";
import axios from "axios";

export default {
  name: "App",

  components: {
    AppNavigation,
    Cards
  },

  data() {
    return {
      tools: []
    };
  },

  beforeMount() {
    this.getTools();
  },

  methods: {
    async getTools() {
      try {
        const response = await axios("./card-data.json");
        this.tools = await response.data;
        console.log(this.tools);
      } catch (e) {
        console.log(e);
      }
    }
  }
};
</script>
