<nav class="back-nav">
  <a href="/" class="back-button">← Back</a>
</nav>

<slot />

<style>
  .back-nav {
    position: fixed;
    top: 1rem;
    right: 1rem;
    z-index: 100;
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
</style> 
