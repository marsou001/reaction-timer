<template>
  <h1 class='header'>Ninja Reaction Timer</h1>
  <button class='play'>Play</button>
</template>

<script>
export default {
  name: 'Play',  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.play {
  color: rgb(238, 228, 228);
  background-color: rgb(27, 172, 83);
  padding: 10px 15px;
  border: none;
  border-radius: 3px;
  cursor: pointer;  
  transition-property: background-color;
  transition-duration: 0.2s;;
}
.play:hover {
  background-color: rgb(16, 148, 67);
}
</style>
