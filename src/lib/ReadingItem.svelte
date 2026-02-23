<script>
  export let data = {};
</script>

<article class="reading-card">
  <img src={data.image} alt="Cover of {data.title}" />
  
  <div class="details">
    <h3>{data.title}</h3>
    <p class="author">By {data.author}</p>
    
    {#if data.rating}
      <p class="rating">{data.rating}</p>
    {/if}
  </div>
</article>

<style>
  .reading-card {
    display: flex; 
    gap: 1em;
    align-items: start;
    margin-bottom: 1.5em;
  }

  img {
    width: 100px;
    height: auto;
    aspect-ratio: 2 / 3;
    object-fit: cover;
    border-radius: 4px;
  }

  h3 {
    margin: 0;
    font-size: 1.1em;
  }

  .author {
    font-style: italic;
    margin: 0.2em 0;
    color: var(--color-accent);
  }

  .rating {
    margin: 0;
    font-size: 0.9em;
    color: #666;
    line-height: 1.4;
  }
</style>