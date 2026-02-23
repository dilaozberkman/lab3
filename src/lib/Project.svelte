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