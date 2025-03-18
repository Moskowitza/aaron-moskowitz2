<nav class="top-nav">
  <a href="/" class="nav-brand">Aaron Moskowitz</a>
  <div class="nav-sections">
    <a href="/about">About</a>
    <div class="dropdown">
      <span>Pets</span>
      <div class="dropdown-content">
        <a href="/pets/elton">Elton</a>
        <a href="/pets/moog">Moog</a>
        <a href="/pets/eno">Eno</a>
        <a href="/pets/toki">Toki</a>
      </div>
    </div>
    <div class="dropdown">
      <span>Technology</span>
      <div class="dropdown-content">
        <a href="/technology/macbook-transition">MacBook Transition</a>
      </div>
    </div>
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

  .dropdown {
    position: relative;
    cursor: pointer;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    background: white;
    min-width: 160px;
    box-shadow: 0 8px 16px rgba(0,0,0,0.1);
    padding: 0.5rem 0;
    z-index: 1;
  }

  .dropdown:hover .dropdown-content {
    display: flex;
    flex-direction: column;
  }

  .dropdown-content a {
    padding: 0.5rem 1rem;
  }

  .dropdown-content a:hover {
    background: #f5f5f5;
  }
</style> 
