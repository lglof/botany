<template>
  <div class="wrapper" ref="wrapper">
    <Sidebar v-on:itemclick="newFlower($event)" />
  </div>
</template>

<script>
import Flower from "./Flower";
import Sidebar from "./Sidebar";
import Vue from "vue";
var FlowerClass = Vue.extend(Flower);

export default {
  name: "Workbench",
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Flower,
    Sidebar
  },
  methods: {
    newFlower(eventData) {
      console.log(eventData);
      var FlowerInstance = new FlowerClass({
        propsData: {
          species: eventData.species,
          colour: eventData.colour
        }
      });
      FlowerInstance.$mount();
      this.$refs.wrapper.appendChild(FlowerInstance.$el);
    }
  }
};
</script>

<style scoped>
.wrapper {
  position: fixed;
  outline: 3px black solid;
  height: 100%;
  width: 100%;
}
</style>
