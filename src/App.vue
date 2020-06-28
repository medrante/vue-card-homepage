<template>
  <v-app>
    <AppNavigation />
    <Cards :tools="tools" />
    <!-- <p>{{ tools }}</p> -->
  </v-app>
</template>

<script>
import AppNavigation from "./components/AppNavigation";
import Cards from "./components/Cards";

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
        const res = await fetch("./card-data.json");
        const data = await res.json();
        console.log(data);
        this.tools = data;
      } catch (e) {
        console.log(e);
      }
    }
  }
};
</script>
