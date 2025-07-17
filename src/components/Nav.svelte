<nav class="top-nav">
  <a href="/" class="nav-brand">Aaron Moskowitz</a>
  <div class="nav-sections">
    <a href="/about">About</a>
    <a href="/pets">Pets</a>
    <a href="/technology">Technology</a>
    <a href="/recipes">Recipes</a>
  </div>
</nav>

<style>
  .top-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
  }

  .nav-brand {
    font-family: 'Libre Caslon Display', serif;
    font-size: 1.5rem;
    text-decoration: none;
    color: inherit;
  }

  .nav-sections {
    display: flex;
    gap: 2rem;
    align-items: center;
  }

  .nav-sections a {
    text-decoration: none;
    color: inherit;
    font-family: 'Libre Caslon Text', serif;
  }

  .nav-sections a:hover {
    color: var(--action-primary);
  }

  @media (max-width: 768px) {
    .top-nav {
      margin-bottom: 1rem;
    }
  }
</style> 
