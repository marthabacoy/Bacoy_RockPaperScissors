<template>
    <div>
      <h1> Rock🪨Paper📄Scissors✂️</h1>
      <h1 style="background-color:transparent;">Winner: {{ winner }}</h1>
      <p>Player 1 choice: <u>{{ player1choice }}</u></p>
      <p>Player 2 choice: <u>{{ player2choice }}</u></p>
      <br>
      <button class="normal-button" @click="refreshpage">Play Again</button>
    </div>
  </template>
  
  <script>
  export default {
    // define props for receiving data from the parent component
    props: {
      player1choice: String,
      player2choice: String,
      winner: String
    },
    methods: {
      refreshpage() {
        // refresh page to play again
        location.reload();
      }
    }
  }
  </script>
  