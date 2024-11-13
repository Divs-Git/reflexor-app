<template>
  <div class="container">
    <h1 style="font-size: 3rem">Reflexor</h1>
    <button @click="handleGameStart" :disabled="isPlayerActive">Start</button>
    <AppCard :delay="delay" v-if="isPlayerActive" @end="endGame" />
    <AppResult :score="result" v-if="showResult" />
  </div>
</template>

<script>
import AppCard from './components/AppCard.vue'
import AppResult from './components/AppResult.vue'
export default {
  name: 'App',
  components: {
    AppCard,
    AppResult,
  },
  data() {
    return {
      delay: null,
      isPlayerActive: false,
      showResult: false,
      result: null,
    }
  },

  methods: {
    handleGameStart() {
      this.isPlayerActive = true
      this.showResult = false
      this.delay = 2000 + Math.random() * 5000
    },
    endGame(value) {
      this.result = value
      this.isPlayerActive = false
      this.showResult = true
    },
  },
}
</script>

<style>
@import './App.css';
</style>
