<template>
  <div class="menu_wrapper">
    <div class="menu_contents">
      {{ defaultSpecies[currentSpecies] }}
      <button v-on:click="updateSpecies()">change species</button>
      <SidebarItem
        v-for="defaultColour in defaultColours"
        :key="defaultColour.colour"
        :colour="defaultColour.colour"
        :species="defaultSpecies[currentSpecies]"
      />
    </div>
  </div>
</template>

<script>
import SidebarItem from "./SidebarItem";

export default {
  name: "Sidebar",
  components: {
    SidebarItem
  },
  data: function() {
    return {
      defaultColours: [
        {
          colour: "yellow"
        },
        {
          colour: "red"
        },
        {
          colour: "white"
        }
      ],
      defaultSpecies: ["cosmos", "windflowers"],
      currentSpecies: 0
    };
  },
  methods: {
    updateSpecies() {
      let i = (this.currentSpecies + 1) % this.defaultSpecies.length;
      this.currentSpecies = i;
    }
  }
};
</script>

<style scoped>
.menu_wrapper {
  position: fixed;
  width: 10%;
  height: 70%;
}
.menu_contents {
  background: wheat;
  width: 100%;
  height: 100%;
}
</style>
