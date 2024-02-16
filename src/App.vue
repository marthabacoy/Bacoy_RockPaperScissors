<template>
  <div id="app">
    <div v-if="!playerOneChoice">
      <PlayerOne @player-one-choice="handlePlayerOneChoice" />
    </div>
    <div v-else-if="!playerTwoChoice">
      <PlayerTwo @player-two-choice="handlePlayerTwoChoice" />
    </div>
    <div v-else>
      <GameResult :playerOneChoice="playerOneChoice" :playerTwoChoice="playerTwoChoice" :winner="calculateWinner(playerOneChoice, playerTwoChoice)" />
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
      playerOneChoice: null,
      playerTwoChoice: null,
    };
  },
  methods: {
    handlePlayerOneChoice(choice) {
      this.playerOneChoice = choice;
    },
    handlePlayerTwoChoice(choice) {
      this.playerTwoChoice = choice;
    },
    calculateWinner(choice1, choice2) {
      if (choice1 === choice2) {
        return "It's a tie!";
      } else if (
        (choice1 === 'rock' && choice2 === 'scissors') ||
        (choice1 === 'scissors' && choice2 === 'paper') ||
        (choice1 === 'paper' && choice2 === 'rock')
      ) {
        return "Player One wins!";
      } else {
        return "Player Two wins!";
      }
    }
  }
}
</script>
