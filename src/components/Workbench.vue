<template>
  <div class="wrapper">
    <Flower species="windflower" colour="white" />
    <Flower species="cosmos" colour="yellow" />
    <button v-on:click="newFlower()">New Flower!</button>
  </div>
</template>

<script>
import Flower from "./Flower";

export default {
  name: "Workbench",
  components: {
    Flower
  },
  methods: {
    newFlower() {
      console.log("NEW FLOWER");
      // TODO: make a flower generator
    }
  }
};
</script>
