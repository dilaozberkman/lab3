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
    <article>
      <h2>{p.title}</h2>
      <img src={p.image} alt={p.title} />
      <p>{p.description}</p>

      {#if p.url}
        <a href={p.url}>View Full Report</a>
      {/if}
    </article>
  {/each}
</div>

<style>
  /* Step 2.1: CSS inside a <style> block only applies to this page [cite: 157] */
  .projects {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(15em, 1fr));
    gap: 1em;
  }

  article {
    border: 1px solid #ccc;
    padding: 1em;
    border-radius: 8px;
  }

  article img {
    width: 100%;
    height: auto;
  }
</style>
