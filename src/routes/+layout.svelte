<script>
    import { base } from "$app/paths";
    let pages = [
        {url: "/", title: "Home"},
        {url: "/projects", title: "Projects"},
        {url: "/resume", title: "CV"},
        {url: "/contact", title: "Contact"},
        {url: "https://github.com/dilaozberkman", title: "Github"},
        ];
</script>

<nav>
  {#each pages as p}
    <a href={base + p.url}>
      {p.title}
    </a>
  {/each}
</nav>

<slot />