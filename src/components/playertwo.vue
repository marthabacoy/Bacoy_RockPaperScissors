<template>
  <div>
    <h1> Rock🪨Paper📄Scissors✂️</h1>
    <h2>Your Move! <br> Player 2:</h2>
    <br><br>
    <div style="display:flex">
      <button class="custom-button" style="background-image: url('src/assets/rock.png');" @click="choose('rock')">
        <h3>rock</h3>
      </button>
      <button class="custom-button" style="background-image: url('src/assets/paper.png');" @click="choose('paper')">
        <h3>paper</h3>
      </button>
      <button class="custom-button" style="background-image: url('src/assets/scissors.png');" @click="choose('scissors')">
        <h3>scissors</h3>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  // method triggered when player chooses
  methods: {
    choose(choice) {
      // create a custom event player2move
      this.$emit('player2move', choice);
    },
  }
}
</script>
