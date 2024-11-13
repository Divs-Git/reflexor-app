<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click Me</div>
</template>

<script>
export default {
  name: 'AppCard',
  props: {
    delay: {
      type: Number,
    },
  },
  emits: ['end'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },

  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    },
  },
}
</script>

<style scoped>
.block {
  background: linear-gradient(135deg, #a18cd1, #fbc2eb);
  border-radius: 12px;
  color: #fff;
  text-align: center;
  width: 400px;
  border-radius: 20px;
  padding: 100px 0;
  margin: 40px auto;
  cursor: pointer;
}
</style>
