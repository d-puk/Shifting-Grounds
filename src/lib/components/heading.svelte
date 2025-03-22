<script>
    import introBeans from '../../assets/introBeans.png';
</script>

<div class="heading">
    <div class="title">
        <h1>Shifting</h1>
        <img src="{introBeans}" alt="Two coffee beans, one healthy and one burnt">
        <h1>Grounds</h1>
    </div>
    <div class="subtext">
        <h4>March 2025</h4>
        <h3>Coffee and the climate crisis</h3>
        <h4>By Deepak Ramarao</h4>
    </div>
</div>

<style>
    .heading {
        display: flex;
        width: 95%;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border-top: 1px solid var(--border-strong, #B0AFBA);
        border-bottom: 1px solid var(--border-strong, #B0AFBA);
    }

    .title {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1.25rem;
        align-self: stretch;
    }

    img {
        height: 5rem;
        aspect-ratio: 130.15/96.00;
    }

    .subtext {
        display: flex;
        padding: var(--spacing-2, 1rem) 0rem;
        justify-content: space-between;
        align-items: center;
        align-self: stretch;

        border-top: 1px solid var(--border-strong, #B0AFBA);
    }

    .subtext h3 {
        position: absolute;
        left: 50%;
        transform: translate(-50%);
    }
</style>