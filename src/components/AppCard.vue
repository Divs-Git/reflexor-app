<template>
  <div class="block" v-if="showBlock">Click Me</div>
</template>

<script>
export default {
  name: 'AppCard',
  props: {
    delay: {
      type: Number,
    },
  },
  data() {
    return {
      showBlock: false,
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
    }, this.delay)
  },
}
</script>

<style scoped>
.block {
  width: 400px;
  border-radius: 20px;
  background-color: var(--bg-card);
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
