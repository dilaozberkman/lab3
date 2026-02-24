<svelte:head>
  <title>Contact me | Dila Ozberkman</title>
</svelte:head>

<nav class="menu">
  <ul>
    <li><a href=".">Home</a></li>
    <li><a href="projects">Projects</a></li>
    <li><a href="contact" class="current">Contact</a></li>
    <li><a href="https://github.com/dilaozberkman" target="_blank">Profile</a></li>
    <li><a href="resume">CV</a></li>
  </ul>
</nav>

<h1>Contact me!</h1>

<form action="mailto:dilao003@mit.edu" method="get" enctype="text/plain">
    <label>
      Email:
      <input type="email" id="email" name="email">
    </label>
    <label>
      Subject:
      <input id="subject" name="subject">
    </label>
    <label>
      Body:
      <textarea id="body" name="body"></textarea>
    </label>
    <button type="submit">Submit!</button>
</form>

<style>
  /* Step 2.1: Add any CSS here that is specific to your contact form.
     Svelte will ensure these styles don't leak to other pages.
  */
  form {
    display: grid;
    gap: 1em;
    max-width: 400px;
    width: 100%;
  }

  label {
    display: grid;
    grid-template-columns: 10rem 1fr;
  }

  input, textarea {
    width: 100%;
    margin-top: 0.5em;
  }
</style>
