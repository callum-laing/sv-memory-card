<script>
let cards = [1, 2, 3, 4, 5];
let previousNumber = null;

let shuffleCards = () => {
    for (let i = cards.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [cards[i], cards[j]] = [cards[j], cards[i]];
    }
}

let clickButton = (number) => {
    
    if (number === previousNumber) {
        console.log("Game over!!!");
    }
    shuffleCards();
    previousNumber = number;

}

</script>

<div class="cardContainer">
    {#each cards as card (card)}
    <button on:click={() => clickButton(card)} class="card">{card}</button>
{/each}
</div>

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
    }
</style>