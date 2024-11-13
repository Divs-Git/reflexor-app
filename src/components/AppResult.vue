<template>
  <div class="result">Reaction Time: {{ score }} ms</div>
</template>

<script>
export default {
  name: 'AppResult',
  props: {
    score: {
      type: Number,
    },
  },
}
</script>

<style>
.result {
  margin-top: 2rem;
  font-size: large;
}
</style>
