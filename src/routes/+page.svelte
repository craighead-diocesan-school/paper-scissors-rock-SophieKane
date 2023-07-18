<script>
  let userAnswer = ""
  let computerAnswer = ""
  let answers = ["paper", "scissors", "rock"]
  let result = ""
  function paper() {
    userAnswer = "paper"
    getComputerAnswer()
  }
  function scissors() {
    userAnswer = "scissors"
    getComputerAnswer()
  }
  function rock() {
    userAnswer = "rock"
    getComputerAnswer()
  }
  function getComputerAnswer() {
    let index = Math.floor(Math.random(0) * answers.length)
    computerAnswer = answers[index]
    getResult()
  }
  function getResult() {
    if (userAnswer == computerAnswer) {
      result = "It's a draw"
    } else if (userAnswer == "paper") {
      if (computerAnswer == "scissors") {
        result = "Computer wins"
      } else {
        result = "User wins"
      }
    } else if (userAnswer == "scissors") {
      if (computerAnswer == "rock") {
        result = "Computer wins"
      } else {
        result = "User wins"
      }
    } else {
      if (computerAnswer == "paper") {
        result = "Computer wins"
      } else {
        result = "User wins"
      }
    }
  }
</script>

<button on:click={paper}>Paper</button>
<button on:click={scissors}>Scissors</button>
<button on:click={rock}>Rock</button>

<br />

{#if userAnswer == "paper"}
  <img src="paper 2.png" alt="paper" />
{:else if userAnswer == "scissors"}
  <img src="scissors 3.png" alt="scissors" />
{:else if userAnswer == "rock"}
  <img src="rock 2.png" alt="rock" />
{/if}

{#if computerAnswer == "paper"}
  <img src="paper 2.png" alt="paper" />
{:else if computerAnswer == "scissors"}
  <img src="scissors 3.png" alt="scissors" />
{:else if computerAnswer == "rock"}
  <img src="rock 2.png" alt="rock" />
{/if}

<p>You chose {userAnswer}. The computer chose {computerAnswer}</p>
<br />
{result}

<!-- <script>
  let userAnswer = ""
  let computerAnswer = ""
  let answers = ["paper", "scissors", "rock"]
  let result = ""

  function showUserPicture() {
    userAnswer = userAnswer.toLowerCase()
  }

  function getComputerAnswer() {
    let index = Math.floor(Math.random(0) * answers.length)
    computerAnswer = answers[index]
  }

  function getResult() {
    if (userAnswer == "paper") {
      if (computerAnswer == "paper") {
        result = "It's a tie!"
      } else if (computerAnswer == "scissors") {
        result = "You lost!"
      } else if (computerAnswer == "rock") {
        result = "You won!"
      }
    } else if (userAnswer == "scissors") {
      if (computerAnswer == "paper") {
        result = "You won!"
      } else if (computerAnswer == "scissors") {
        result = "It's a tie!"
      } else if (computerAnswer == "rock") {
        result = "You lost!"
      }
    } else if (userAnswer == "rock") {
      if (computerAnswer == "paper") {
        result = "You lost!"
      } else if (computerAnswer == "scissors") {
        result = "You won!"
      } else if (computerAnswer == "rock") {
        result = "It's a tie!"
      }
    }
  }
</script>

<h1>Paper, Scissors, Rock</h1>

<label>
  Rock, Paper or Scissors?
  <input bind:value={userAnswer} />
</label>

<button on:click={showUserPicture}>Go</button>

<br />

{#if userAnswer == "paper"}
  <img src="paper 2.png" alt="paper" />
{:else if userAnswer == "scissors"}
  <img src="scissors 3.png" alt="scissors" />
{:else if userAnswer == "rock"}
  <img src="rock 2.png" alt="rock" />
{:else}
  <h3>It appears you have not entered a valid answer. Please try again</h3>
{/if}

<br />

<button on:click={getComputerAnswer}>Generate Computer Answer</button>

<br />

{#if computerAnswer == "paper"}
  <img src="paper 2.png" alt="paper" />
{:else if computerAnswer == "scissors"}
  <img src="scissors 3.png" alt="scissors" />
{:else if computerAnswer == "rock"}
  <img src="rock 2.png" alt="rock" />
{/if}

<br />

<button on:click={getResult}>Get Result</button>

<br />

{result}

<style>
  img {
    width: 15em;
  }
</style> -->

<style>
  img {
    width: 15em;
  }
</style>
