<script>
  import Heading from "./lib/components/heading.svelte";
  import Intro from "./lib/Intro.svelte";
  import Outro from "./lib/Outro.svelte";

  import { onMount } from "svelte";
  import ScrollyMap from "./lib/components/scrollyMap.svelte";
  import StorySection from "./lib/components/storySection.svelte";

  // Importing story data from storyData.js
  import { storyData } from "./data/storyData.js";

  // Tracking section in view so that map in view can change 
  let currentSectionIndex = 0; 

  // Observer for tracking the section in view
  onMount(() => {
    const options = {
      root: null, // Viewport is root 
      rootMargin: '-40% 0px -40% 0px', // trigger area in the middle 20% of the screen
      threshold: 0, // trigger as soon as any part enters
    }; 

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if(entry.isIntersecting) {
          // Find the index of the section that's currently in view
          const index = storyData.findIndex(section => section.id === entry.target.id);
          if(index !== -1) {
            currentSectionIndex = index;
          }
        }
      });
    }, options);

    // Observe all section elements
    document.querySelectorAll('.story-section').forEach(section => {
      observer.observe(section);
    }); 

    return () => {
      observer.disconnect();
    };

  });
</script>

<main>
  <Heading />
  <Intro />

  <div class="scroll-container">
    <!-- ScrollyMap will stick and stay fixed as we scroll -->
     <ScrollyMap currentMapSrc={storyData[currentSectionIndex].mapImage} />
  
     <!-- Story sections that will scroll over the map -->
      <div class="story-content">
        {#each storyData as section, i}
          <StorySection
            id={section.id}
            content={section.content}
          />
        {/each}
      </div>
  </div>

  <Outro />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    box-sizing: border-box;
    padding-inline: 2rem;
    margin-block: var(--spacing-4, 2rem);
  }

  .scroll-container {
    position: relative;
    width: 100%;
    margin-bottom: var(--spacing-4, 2rem);
  }

  .story-content {
    position: relative;
    z-index: 1; /* Above the map */
  }
</style>
