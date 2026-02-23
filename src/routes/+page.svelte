<script>
  import projects from '$lib/projects.json';
  import Project from "$lib/Project.svelte";

  import reading from '$lib/reading.json';
  import ReadingItem from '$lib/ReadingItem.svelte';
</script>

<svelte:head>
    <title>Dila Ozberkman: Personal site and portfolio</title>
</svelte:head>

<nav>
    <ul>
      <li><a href="." class="current">Home</a></li>
      <li><a href="projects">Projects</a></li>
      <li><a href="contact">Contact</a></li>
      <li><a href="https://github.com/dilaozberkman" target="_blank">Profile</a></li>
      <li><a href="resume">CV</a></li>
    </ul>
</nav>

<h1>Dila Ozberkman</h1>
<p>
    I am a (super) senior at MIT double majoring in Architecture and Urban Planning. I am from Cyprus!
</p>

<img
    class="fit-picture"
    width="150"
    height=auto
    src="images/dila_pic.jpg"
    alt="Dila outside MIT Building 8 on a sunny day"
/>

<section>
  <h2>What I'm Reading!</h2>
  
  <div class="reading-list">
    {#each reading as item}
      <ReadingItem data={item} />
    {/each}
  </div>
</section>

<h2>Latest Projects</h2>

<div class="projects"> {#each projects.slice(0, 3) as p}
        <Project data={p} />
    {/each}
</div>

<style>
  .projects {
    display: grid;
    grid-template-columns: repeat(3, 1fr); 
    gap: 2em;
    margin-top: 2em;
  }
  .projects :global(h2) {
    font-size: 150%; 
  }

  .reading-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
    margin-top: 1rem;
  }
</style>