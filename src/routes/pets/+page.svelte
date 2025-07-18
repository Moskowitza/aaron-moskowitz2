<svelte:head>
  <title>Pets</title>
  <meta name="description" content="Meet Aaron's beloved pets - Elton, Moog, Eno, Blue, and Toki. Each with their own unique personality and story to share." />
</svelte:head>

<section class="container">
  <h1 class="name">Pets</h1>
  
  <nav class="back-nav">
    <a href="/" class="back-button">← Back</a>
  </nav>

  <div class="pet-list">
    <a href="/pets/elton">Elton</a>
    <a href="/pets/eno">Eno</a>
    <a href="/pets/moog">Moog</a>
    <a href="/pets/blue">Blue</a>
    <a href="/pets/toki">Toki</a>
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

  .pet-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .pet-list a {
    font-family: 'Libre Caslon Text', serif;
    font-size: 1.2rem;
    text-decoration: none;
    color: var(--text-primary);
    padding: 0.5rem;
    border-radius: 4px;
    transition: background-color 0.2s;
  }

  .pet-list a:hover {
    background-color: var(--surface-hover);
  }
</style>
