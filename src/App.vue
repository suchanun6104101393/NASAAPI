<template>
  <div id="app">
    <search></search>
  </div>
</template>
<script>
import Search from "./components/Search";
export default {
  name: "app",
  components: {
    Search,
  },
};
</script>
<style>
#app {
 font-family: 'Finger Paint', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: darkorange;
  margin-top: 60px;
  background-color: black;
}
h1 {
  color: darksalmon;
  font-size: larger;
}
</style>
