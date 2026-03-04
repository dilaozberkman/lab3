<script>
    import { base } from "$app/paths";
    import { page } from "$app/stores";
    import "../style.css";

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
      class:current={p.url === "/" 
        ? $page.url.pathname === (base + "/")
        : $page.url.pathname.startsWith(base + p.url)}
      target={p.url.startsWith("http") ? "_blank" : null}
    >
      {p.title}
    </a>
  {/each}
</nav>

<style>
    :global(html) {
        color-scheme: light dark;
        }

    nav {
        --border-color: oklch(50% 10% 200 / 40%);
        display: flex; /* Turns nav into a flex container */
        margin-bottom: 1em;
        border-bottom-width: 1px;
        border-bottom-style: solid;
        border-bottom-color: var(--border-color);
    }

    nav a {
        flex: 1; /* step 2.2 for each element to take the same space  */
        text-decoration: none; /* Remove the underline from the links by setting */
        color: inherit;
        text-align: center;
        padding: 0.5em;
    }
            nav a.current {
                --border-color: oklch(50% 10% 200 / 40%);
                border-bottom-width: 0.4em;
                border-bottom-style: solid;
                border-bottom-color: var(--border-color);
                padding-bottom: 0.1em;
                font-weight: bold;
    }

    nav a:hover {
        /* Add here hover effects */
        border-bottom-width: 0.4em;
        border-bottom-style: solid;
        border-bottom-color: var(--color-accent);
        padding-bottom: 0.1em;
        background-color: color-mix(in oklch, var(--color-accent), canvas 85%);
    }
</style>

<slot />