<script>
    import { fade } from "svelte/transition";

    export let currentMapSrc;

    let previousMapSrc = '';
    let transitionDuration = 500; // Duration in ms

    //Watch for changes in the currentMapSrc and update accordingly
    $: if(currentMapSrc !== previousMapSrc && previousMapSrc !== '') {
        // When the map changes, update the previous
        previousMapSrc = currentMapSrc;
    } else if (previousMapSrc === '') {
        // Initialise on first load
        previousMapSrc = currentMapSrc;
    }

    function getMapPath(mapName) {
        // Using dynamic imports with Vite
        return new URL(`../../assets/maps/${mapName}`, import.meta.url).href;
        // src="{`/maps/${currentMapSrc}`}"
    }
</script>

<div class="map-container">
    {#key currentMapSrc}
        <img 
            class="map-image" 
            src={getMapPath(currentMapSrc)} 
            alt="Maps of changes in the coffee belt"
            transition:fade={{ duration: transitionDuration }}
        >
    {/key}
</div>

<style>
    .map-container {
        position: sticky;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        z-index: 0; /* Placed behind content */
        overflow: hidden;
    }

    .map-image {
        width: 100%;
        height: 100vh;
        object-fit: cover; /* Cover container and maintain aspect ratio */
        position: absolute;
        top: 0;
        left: 0;
    }
</style>