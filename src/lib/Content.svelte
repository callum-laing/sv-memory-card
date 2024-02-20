<script>
let cards = [1, 2, 3, 4, 5];
let previousNumber = null;
let score = 0;
let highScore = 0;
let gameActive = true;

let shuffleCards = () => {
    for (let i = cards.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [cards[i], cards[j]] = [cards[j], cards[i]];
    }
}

let clickButton = (number) => {
    if (!gameActive) return;
    
    if (number === previousNumber) {
        alert(`Game over! Your score was ${score}.`);
        gameActive = false;
        if (score > highScore) {
            highScore = score;
        }
        score = 0;
    } else {
        score += 1;
    }

    shuffleCards();
    previousNumber = number;
    console.log(score);
}

let startGame = () => {
    gameActive = true;
    score = 0;
    previousNumber = null;
    shuffleCards();
};

</script>
<h2>High Score: {highScore}</h2>
{#if gameActive}
<div class="cardContainer">
    {#each cards as card (card)}
    <button on:click={() => clickButton(card)} class="card">{card}</button>
{/each}
</div>
<h2>Current score: {score}</h2>
{:else}
<div class="startButton">

    <button on:click={startGame}>START GAME</button>

</div>
{/if}


<style>
    .cardContainer {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .card {
        text-align: center;
        height: 300px;
        width: 200px;
        border: 2px solid rgba(150, 150, 250);
        margin: 20px;
        border-radius: 10px;
        background-color: black;
        color: white;
        font-size: 4rem;
        cursor: pointer;
    }

    .card:hover {
        border: 2px solid white;
    }

    .startButton {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .startButton > button {
        width: 200px;
        height: 50px;
        font-size: 1.5rem;
        border-radius: 10px;
        cursor: pointer;
        background-color: black;
        color: white;
        border: 2px solid rgba(150, 150, 250);
    }

    .startButton > button:hover {
        border: 2px solid white;
    }

    h2 {
        margin-left: 20px;
    }
</style>