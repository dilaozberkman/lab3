<script>
    export let data = {};
</script>

<article>
      <h2>{data.title}</h2>
      <img src={data.image} alt={data.title} />
      <p>{data.description}</p>

      {#if data.url}
        <a href={data.url}>View Full Report</a>
      {/if}
    </article>

<style>
  /* Step 5.4: Styles moved from style.css */
  article {
    display: grid;
    grid-template-rows: subgrid;
    grid-row: span 3;
    gap: 0.5em; /* Optional: adds nice spacing between title/img/text */
  }

  h2 {
    margin: 0;
    /* You can add your smaller font size here too! */
    font-size: 1.2rem; 
  }

  img {
    max-width: 100%;
    height: auto;
  }
</style>