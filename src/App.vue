<template>
  <div class="container m-auto d-flex flex-column justify-content-center align-items-center gap-5">
    <h1 class="text-center">Ninja Reaction Timer</h1>
    <button @click="startGame" :disabled="isStarted" class="btn btn-success">Start Game</button>
    <Block v-if="isStarted" :delay="delay" @end="endGame" />
    <h4 v-if="showResults">Reaction Time {{ score }} ms </h4>
  </div>
</template>

<script>
import Block from "./components/Block.vue";
export default {
  components: {
    Block
  },
  data() {
    return {
      delay: null,
      isStarted: false,
      score: 0,
      showResults: false,

    }
  },

  methods: {
    startGame() {
      this.isStarted = true,
        this.delay = Math.random() * 5000,
        console.log(this.delay),
        this.showResults = false
    },
    endGame(reactionTime) {
      this.isStarted = false,
        this.score = reactionTime,
        this.showResults = true
    }
  }
}
</script>
