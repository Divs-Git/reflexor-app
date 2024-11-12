<template>
  <div class="container">
    <h1>Reflexor</h1>
    <button @click="handleGameStart" :disabled="isPlayerActive">Start</button>
    <AppCard :delay="delay" v-if="isPlayerActive" />
  </div>
</template>

<script>
import AppCard from './components/AppCard.vue'
import AppResult from './components/AppResult.vue'
export default {
  name: 'App',
  components: {
    AppCard,
  },
  data() {
    return {
      delay: null,
      isPlayerActive: false,
    }
  },

  methods: {
    handleGameStart() {
      this.isPlayerActive = true
      this.delay = 2000 + Math.random() * 5000
    },
  },
}
</script>

<style>
@import './App.css';
</style>
