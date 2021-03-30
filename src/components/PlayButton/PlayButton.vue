<template>
    <button class="play" @click="startGame" :disabled="gameStarted">Play</button>
</template>

<script>
export default {
    name: 'PlayButton',
    props: [
        'gameStarted',
    ],
    methods: {
        startGame() {
            this.$emit('start');
        }
    },
}
</script>

<style scoped>
.play {
  color: rgb(238, 228, 228);
  background-color: rgb(27, 172, 83);
  padding: 10px 15px;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  transition-property: background-color;
  transition-duration: 0.2s;
}
.play:hover {
  background-color: rgb(16, 148, 67);
}
.play[disabled] {
  background-color: rgb(99, 189, 133);
  cursor: initial;
}
.play[disabled]:hover {
  background-color: rgb(99, 189, 133);
}
</style>