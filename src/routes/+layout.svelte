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
    let colorScheme = "light dark";
    let root = globalThis.document?.documentElement;
    $: root?.style.setProperty("color-scheme", colorScheme);
</script>

<label class="color-scheme-switch">
  Theme:
  <select bind:value={colorScheme}>
    <option value="light dark">Automatic</option>
    <option value="light">Light</option>
    <option value="dark">Dark</option>
  </select>
</label>

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

    .color-scheme-switch {
        position: absolute; 
        top: 1rem;       
        left: 1rem;   
        
        display: inline-flex;
        gap: 4px;
        font-size: 80%;
    }

    .color-scheme-switch select {
        font-family: inherit;
    }

    nav {
        --border-color: oklch(50% 10% 200 / 40%);
        display: flex; /* Turns nav into a flex container */
        margin-bottom: 1em;
        border-bottom: 4px solid var(--border-color);
    }

    nav a {
        flex: 1; /* step 2.2 for each element to take the same space  */
        text-decoration: none; /* Remove the underline from the links by setting */
        color: inherit;
        text-align: center;
        padding: 0.5em;
    }
            nav a.current {
                border-bottom: 4px solid var(--border-color);
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