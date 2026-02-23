<script>
  import projects from '$lib/projects.json';
  import Project from "$lib/Project.svelte";
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
    width="500"
    height="667"
    src="images/dila_pic.jpg"
    alt="Dila outside MIT Building 8 on a sunny day"
/>

<div class="projects highlights">
    <h3>Latest Projects</h3>
    {#each projects.slice(0, 3) as p}
        <Project data={p} />
    {/each}
</div>