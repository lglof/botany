<template>
  <div class="menu_wrapper">
    <div class="menu_contents">
      Hopefully to be a sidebar
    </div>
  </div>
</template>

<script>
export default {
  name: "Sidebar"
}
</script>

<style scoped>
.menu_wrapper {
  position: fixed;
  display: grid;
  grid-template: repeat(5, 20%);
}
.menu_contents {
  background: wheat;
  grid-area: 2 / 5 / 1 / 2;
}
</style>
