<template>
  <div>
    <img :src="imageSource()" />
  </div>
</template>

<script>
export default {
  name: "Flower",
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
