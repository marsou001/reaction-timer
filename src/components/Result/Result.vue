<template>
  <div class="result" v-if="hasResult">
    <span class='result-description'>{{ resultDescription }}</span>...
    <br />
    <span class='result-time'>Reaction time - {{ result }}</span>
  </div>  
</template>

<script>
export default {
  name: "Result",
  props: [
      "result",
      "hasResult",
      "resultDescription",
    ],
};
</script>

<style scoped>
.result {
  margin-top: 60px;
}
.result-time {
  display: inline-block;
  margin-top: 1.5rem;
}
.result-description {
    font-size: 1.6rem;
    font-weight: 600;
    color: rgb(27, 172, 83);
}
</style>