<svelte:head>
  <title>Recipes</title>
</svelte:head>

<section class="container">
  <h1 class="name">Recipes</h1>
  
  <nav class="back-nav">
    <a href="/" class="back-button">← Back</a>
  </nav>

  <div class="recipe-list">
    <!-- <a href="/recipes/choclate-mouse-pie">Choclate Mouse Pie</a> -->
    <a href="/recipes/cookies">Cookies</a>
    <a href="/recipes/kale">Kale</a>
    <a href="/recipes/pizza-dough">Pizza Dough</a>
    <a href="/recipes/vegan-chicken-pie">Vegan Chicken Pie</a>
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



  .recipe-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .recipe-list a {
    font-family: 'Libre Caslon Text', serif;
    font-size: 1.2rem;
    text-decoration: none;
    color: var(--text-primary);
    padding: 0.5rem;
    border-radius: 4px;
    transition: background-color 0.2s;
  }

  .recipe-list a:hover {
    background-color: var(--surface-hover);
  }
</style> 
