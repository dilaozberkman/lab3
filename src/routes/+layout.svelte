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
    <a 
      href={p.url.startsWith("http") ? p.url : base + p.url}
      target={p.url.startsWith("http") ? "_blank" : null}
    >
      {p.title}
    </a>
  {/each}
</nav>

<slot />