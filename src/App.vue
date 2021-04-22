<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <!-- bind is necessary due to the fact that I'm using a variable to pass on a value -->
  <Block v-if="isPlaying" :delay="delay" @finish="endGame"/>
	<Results v-if="showResults" :score="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {
    Block,
    Results,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
			score: null,
			showResults: false,
    }
  },
  methods: {
    start() {
      //generates a random time between 1 and 5 seconds
      this.delay = 1000 + Math.random() * 4000
			this.showResults = false
      this.isPlaying = true
    },
		endGame(reactionTime) {
			this.isPlaying = false
			this.showResults = true
			this.score = reactionTime
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
