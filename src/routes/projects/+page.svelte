<script>
  import projects from '$lib/projects.json';
  import Project from "$lib/Project.svelte";
</script>

<svelte:head>
  <title>Projects | Dila Ozberkman</title>
</svelte:head>

<nav class="menu">
  <ul>
    <li><a href=".">Home</a></li>
    <li><a href="projects" class="current">Projects</a></li>
    <li><a href="contact">Contact</a></li>
    <li><a href="https://github.com/dilaozberkman" target="_blank">Profile</a></li>
    <li><a href="resume">CV</a></li>
  </ul>
</nav>

<h1>{projects.length} Projects</h1>

<div class="projects">
  {#each projects as p}
    <Project data={p} />
  {/each}
</div>

<style>
  /* Step 2.1: CSS inside a <style> block only applies to this page [cite: 157] */
  .projects {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(15em, 1fr));
    gap: 1em;
  }

  article img {
    width: 100%;
    height: auto;
  }
</style>
