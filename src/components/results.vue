<template>
    <div>
      <h1>Game Result</h1>
      <p>Player 1 choice: {{ playerOneChoice }}</p>
      <p>Player 2 choice: {{ playerTwoChoice }}</p>
      <p>Winner: {{ winner }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      playerOneChoice: String,
      playerTwoChoice: String,
      winner: String
    }
  }
  </script>
  