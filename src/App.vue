<template>
  <h1 class="header">Ninja Reaction Timer</h1>
  <button class="play" @click="startGame" :disabled="gameStarted">Play</button>
  <div class="target" v-if="showBox" @click="endGame">
    click me
  </div>
  <div class="result" v-if="hasResult">
    {{ result }}
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      timeout: (Math.random() * 3000).toFixed(0),
      gameStarted: false,
      showBox: false,
      timerStart: 0,
      timerEnd: 0,
      result: 0,
      hasResult: false,
    };
  },
  methods: {
    startGame() {
      this.gameStarted = true;      
      this.timerStart = 0;
      this.timerEnd = 0;
      this.result = 0;
      this.hasResult = false;
      setTimeout(() => {
        this.showBox = true;
        this.timerStart = Date.now();
      }, this.timeout);
    },
    endGame() {
      this.timerEnd = Date.now();
      this.result = `${this.timerEnd - this.timerStart}ms`;
      this.showBox = false;
      this.gameStarted = false;
      this.hasResult = true;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
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
.target {
  color: white;
  background-color: rgb(27, 172, 83);
  font-size: 1.7em;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 450px;
  height: 200px;
  margin: auto;
  margin-top: 30px;
  border-radius: 6px;
  cursor: pointer;
}
.result {
  margin-top: 60px;
}
</style>
