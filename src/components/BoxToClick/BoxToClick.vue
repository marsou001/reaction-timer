<template>
  <div class="target" @click="endGame">click me</div>
</template>

<script>
export default {
  name: "BoxToClick",
  methods: {
    endGame() {
      this.$emit("end");
    },
  },
};
</script>

<style scoped>
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
</style>
