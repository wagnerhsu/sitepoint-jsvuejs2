<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <staff-directory />
  <search-box @search="onSearch" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import StaffDirectory from "./components/StaffDirectory.vue";
import SearchBox from "./components/SearchBox.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    StaffDirectory,
    SearchBox,
  },
  methods: {
    onSearch(terms) {
      console.log("terms:", terms);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
