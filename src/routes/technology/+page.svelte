<svelte:head>
  <title>Technology</title>
  <meta name="description" content="Explore Aaron's technical adventures and discoveries, from hardware transitions to development challenges and solutions in healthcare technology." />
</svelte:head>

<section class="container">
  <h1 class="name">Technology</h1>
  <nav class="back-nav">
    <a href="/" class="back-button">← Back</a>
  </nav>
  <div class="tech-list">
    <a href="/technology/macbook-transition">MacBook Transition</a>
    <!-- Add more technology links here as you add more pages -->
  </div>
</section>

<style>
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 2rem;
  }

  .name {
    font-family: 'Libre Caslon Display', serif;
    font-size: clamp(2rem, -0.875rem + 8.333vw, 3.5rem);
    margin-bottom: 2rem;
  }

  .back-nav {
    margin-bottom: 2rem;
  }

  .back-button {
    font-family: 'Libre Caslon Text', serif;
    text-decoration: none;
    color: inherit;
    font-size: 1rem;
  }

  .back-button:hover {
    text-decoration: underline;
  }

  .tech-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .tech-list a {
    font-family: 'Libre Caslon Text', serif;
    font-size: 1.2rem;
    text-decoration: none;
    color: var(--text-primary);
    padding: 0.5rem;
    border-radius: 4px;
    transition: background-color 0.2s;
  }

  .tech-list a:hover {
    background-color: var(--surface-hover);
  }
</style>
