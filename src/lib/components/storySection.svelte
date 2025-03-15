<script>
    // Props for each story section
    export let id;
    export let content;
</script>

<section id={id} class="story-section">
    <div class="content-card">
        <p>{content}</p>
    </div>
</section>

<style>
    .story-section {
        min-height: 100vh;
        padding: 2rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .content-card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: var(--spacing-3, 1.5rem);
        max-width: 400px;
        margin: 0;
        background-color: white;
        box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.10);
    }
</style>