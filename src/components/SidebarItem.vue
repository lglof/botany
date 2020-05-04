<template>
  <div class="item-wrapper" ref="flower-wrap">
    <img class="icon" :src="imageSource()" @mousedown="newFlower()" />
  </div>
</template>

<script>
export default {
  name: "SidebarItem",
  props: {
    species: {
      type: String,
      required: true
    },
    colour: {
      type: String,
      required: true
    }
  },
  methods: {
    imageSource() {
      return require(`../assets/flowerImages/${this.species}/${this.colour}.jpg`);
    },
    newFlower() {
      let flowerData = {
        species: this.species,
        colour: this.colour
      };
      console.log(flowerData.species);
      this.$parent.$emit("itemclick", flowerData);
    }
  }
};
</script>

<style scoped>
.icon {
  height: 75px;
  width: 75px;
  border: 2px black solid;
  border-radius: 3px;
}
</style>
