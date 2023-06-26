<script>
  let response = ""
  let computerAnswer = ""
  let answers = ["paper", "scissors", "rock"]
  let result = ""

  function showUserPicture() {
    response = response.toLowerCase()
  }

  function getComputerAnswer() {
    let index = Math.floor(Math.random(0) * answers.length)
    computerAnswer = answers[index]
  }

  function getResult() {
    if (response == "paper") {
      if (computerAnswer == "paper") {
        result = "It's a tie!"
      } else if (computerAnswer == "scissors") {
        result = "You lost!"
      } else if (computerAnswer == "rock") {
        result = "You won!"
      }
    } else if (response == "scissors") {
      if (computerAnswer == "paper") {
        result = "You won!"
      } else if (computerAnswer == "scissors") {
        result = "It's a tie!"
      } else if (computerAnswer == "rock") {
        result = "You lost!"
      }
    } else if (response == "rock") {
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
  <input bind:value={response} />
</label>

<button on:click={showUserPicture}>Go</button>

<br />

{#if response == "paper"}
  <img src="paper 2.png" alt="paper" />
{:else if response == "scissors"}
  <img src="scissors 3.png" alt="scissors" />
{:else if response == "rock"}
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
</style>
