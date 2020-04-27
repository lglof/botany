<template>
  <div id="app">
    <Sidebar />
    <Workbench />
  </div>
</template>

<script>
import Sidebar from "./components/Sidebar";
import Workbench from "./components/Workbench";

export default {
  name: "App",
  components: {
    Sidebar,
    Workbench
  }
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
