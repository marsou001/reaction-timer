<template>
  <div class="result" v-if="hasResult">
    {{ result }}
  </div>
</template>

<script>
export default {
  name: "Result",
  props: [
      "result",
      "hasResult"
    ],
};
</script>

<style scoped>
.result {
  margin-top: 60px;
}
</style>