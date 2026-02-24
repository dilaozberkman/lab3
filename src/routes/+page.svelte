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

<div class="container">
  <section class="profile">
    <h1>Dila Ozberkman</h1>
    <p>I am a (super) senior at MIT double majoring in Architecture and Urban Planning. I am from Cyprus!</p>
    <img class="fit-picture"
    width="400"
    height=auto
    src="images/dila_pic.jpg"
    alt="Dila outside MIT Building 8 on a sunny day"
    />
  </section>

  <aside class="reading-sidebar">
    <h2>What I'm Reading</h2>
    <div class="reading-list">
      {#each reading as item}
        <ReadingItem data={item} />
      {/each}
    </div>
  </aside>
</div>

<h2>Latest Projects</h2>

<div class="projects"> {#each projects.slice(0, 3) as p}
        <Project data={p} />
    {/each}
</div>

<style>
    .container {
    display: flex;
    gap: 4rem;
    align-items: center;
    margin-bottom: 3rem;
  }

  .profile {
    flex: 2;
  }

  .reading-sidebar {
    flex: 1;
    background-color: oklch(from var(--border-gray) 95% 5% h); 
    padding: 1.5rem;
    border-radius: 12px;
  }

  .reading-sidebar h2 {
    margin-top: 0;
    font-size: 1.5rem;
  }
  
  .reading-list {
    display: flex;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    flex-direction: column;
    gap: 1.5rem;
    margin-top: 1rem;
  }

  .projects {
    display: grid;
    grid-template-columns: repeat(3, 1fr); 
    gap: 2em;
    margin-top: 2em;
  }
  .projects :global(h2) {
    font-size: 150%; 
  }
</style>