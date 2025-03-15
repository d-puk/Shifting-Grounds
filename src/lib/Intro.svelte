<script>
    import coffeeBelt from '../../public/maps/02. Coffee Belt.png'
    import priceChanges from '../assets/priceChange.png'
</script>

<div class="intro">
    <img src="{coffeeBelt}" alt="A map of the Coffee Belt">
    <div class="text-column">
        <p>This strip of Earth, between the Tropic of Cancer and Capricorn, is known as the Coffee Belt. It’s a zone with the ideal conditions for the coffee plant’s growth.</p>
        <p>The coffee that we know and love from these parts of the planet are severely threatened. Since 2015, the price of coffee has more than doubled, and it has everything to do with the climate changes that the belt is facing.</p>
    </div>
    <img class="prices" src="{priceChanges}" alt="A comparison of the price of coffee in 2015 and 2025">
</div>

<style>
    .intro {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: var(--spacing-4, 2rem);
        align-items: center;
        padding-bottom: var(--spacing-8, 4rem);
    }

    img {
        width: 100%;
    }

    .prices {
        width: 40%;
        max-width: 560px;
    }
</style>