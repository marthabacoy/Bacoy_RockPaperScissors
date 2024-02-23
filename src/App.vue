<template>
  <div id="app">
    <!-- display player 1 page, render PlayerOne component if no player1choice  -->
    <div v-if="!player1choice">
      <PlayerOne @player1move="handlePlayerOneChoice" />
    </div>
    <!-- display player 2 page, render PlayerTwo component if no player2choice  -->
    <div v-else-if="!player2choice">
      <PlayerTwo @player2move="handlePlayerTwoChoice" />
    </div>
    <!-- calculate and display results  -->
    <div v-else>
      <GameResult :player1choice="player1choice" :player2choice="player2choice" :winner="results(player1choice, player2choice)" />
    </div>
  </div>
</template>

<script>
import PlayerOne from './components/playerone.vue';
import PlayerTwo from './components/playertwo.vue';
import GameResult from './components/results.vue';

export default {
  components: {
    PlayerOne,
    PlayerTwo,
    GameResult
  },
  data() {
    return {
      //variables for player's choices
      player1choice: null,
      player2choice: null,
    };
  },
  methods: {
    // method for updating player1choice variable based on player's choice
    handlePlayerOneChoice(choice) {
      this.player1choice = choice;
    },
    // method for updating player2choice variable based on player's choice
    handlePlayerTwoChoice(choice) {
      this.player2choice = choice;
    },
    // method for determining the winner
    results(choice1, choice2) {
      if (choice1 === choice2) {
        return "It's a tie! 🎉";
      } 
      else if (
        (choice1 === 'rock' && choice2 === 'scissors') ||
        (choice1 === 'scissors' && choice2 === 'paper') ||
        (choice1 === 'paper' && choice2 === 'rock')
      ) {
        return "Player One! 🎉";
      } 
      else {
        return "Player Two! 🎉";
      }
    }
  }
}
</script>
