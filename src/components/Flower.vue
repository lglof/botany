<template>
  <vue-draggable-resizable :w="100" :h="100" class="drag-drop">
    <img :src="imageSource()" />
  </vue-draggable-resizable>
</template>

<script>
import VueDraggableResizable from "vue-draggable-resizable";

export default {
  name: "Flower",
  components: {
    VueDraggableResizable
  },
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
    }
  }
};
</script>

