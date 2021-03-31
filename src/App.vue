<template>
  <Header />
  <PlayButton @start='startGame' :gameStarted='gameStarted' />
  <BoxToClick v-if="showBox" @end='endGame' />
  <Result :result='result' :hasResult='hasResult' :resultDescription='resultDescription' />
</template>

<script>
import Header from "./components/Header/Header";
import PlayButton from "./components/PlayButton/PlayButton";
import BoxToClick from "./components/BoxToClick/BoxToClick";
import Result from "./components/Result/Result";

export default {
  name: "App",
  components: {
    Header,
    PlayButton,
    BoxToClick,
    Result,
  },
  data() {
    return {
      timeout: (Math.random() * 3000).toFixed(0),
      gameStarted: false,
      showBox: false,
      timerStart: 0,
      timerEnd: 0,
      result: 0,
      hasResult: false,
      resultDescription: '',
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
      this.resultDescription = (this.timerEnd - this.timerStart) < 500 ? 'Fast Reaction' : 'Snail Pace';
    },
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
</style>
