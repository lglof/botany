<template>
  <div class="wrapper">
    <Flower species="windflower" colour="white" />
    <Flower species="cosmos" colour="yellow" />
    <button v-on:click="newFlower()">New Flower!</button>
    <div ref="container" />
  </div>
</template>

<script>
import Flower from "./Flower";
import Vue from "vue";
var FlowerClass = Vue.extend(Flower);

export default {
  name: "Workbench",
  components: {
    Flower
  },
  methods: {
    newFlower() {
      var FlowerInstance = new FlowerClass({
        propsData: { species: "cosmos", colour: "pink" }
      });
      FlowerInstance.$mount();
      this.$refs.container.appendChild(FlowerInstance.$el);
    }
  }
};
</script>
