<template>
  <div>
    <h1>Player 2: Choose your move</h1>
    <button @click="choose('rock')">Rock</button>
    <button @click="choose('paper')">Paper</button>
    <button @click="choose('scissors')">Scissors</button>
  </div>
</template>

<script>
export default {
  methods: {
    choose(choice) {
      this.$emit('player-two-choice', choice);
    },
  }
}
</script>
