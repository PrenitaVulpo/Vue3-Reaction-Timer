<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <!-- bind is necessary due to the fact that I'm using a variable to pass on a value -->
  <Block v-if="isPlaying" :delay="delay"/>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {
    Block,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
    }
  },
  methods: {
    start() {
      //generates a random time between 1 and 5 seconds
      this.delay = 1000 + Math.random() * 4000
      this.isPlaying = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
