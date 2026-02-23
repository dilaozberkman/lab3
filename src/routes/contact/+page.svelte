<svelte:head>
  <title>Contact me</title>
</svelte:head>

<body>
    <h1>Contact me!</h1>
</body>
<form action="mailto:dilao003@mit.edu" method="get" enctype="text/plain">
    <label>Email:
      <input type="email" id="email" name="email">
    </label>
    <label>Subject:
      <input id="subject" name="subject">
    </label>
    <label>Body:
      <textarea id="body" name="body"></textarea>
    </label>
    <button type="submit">Submit!</button>
  </form>
