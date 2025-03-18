<svelte:head>
  <title>Aaron Moskowitz</title>
</svelte:head>

<div class="sections">
  <section class="card">
    <div class="card-content">
      <h2>About Me</h2>
      <p>
        I'm currently the Supervisor of Application Development at Rothman Orthopaedics
        where I build and maintain full stack Javascript applications. With a background
        in Biomedical Engineering, I bring a unique perspective to healthcare technology.
      </p>
    </div>
    <div class="card-links">
      <a href="/about">Read More</a>
    </div>
  </section>

  <section class="card">
    <div class="card-content">
      <h2>Meet the Cats</h2>
      <p>
        Meet our family's beloved cats - Elton, the playful tuxedo cat with a love for
        toe-attacking, and Moog, his adventurous sister. Each has their own unique
        personality and story to share.
      </p>
    </div>
    <div class="card-links">
      <a href="/pets/elton">Meet Elton</a>
      <a href="/pets/moog">Meet Moog</a>
      <a href="/pets/eno">Meet Eno</a>
      <a href="/pets/toki">Meet Toki</a>
    </div>
  </section>

  <section class="card">
    <div class="card-content">
      <h2>Tech Journey</h2>
      <p>
        Follow along with my technical adventures and discoveries, from hardware transitions
        to development challenges and solutions.
      </p>
    </div>
    <div class="card-links">
      <a href="/technology/macbook-transition">MacBook Transition</a>
    </div>
  </section>
  <section class="card">
    <div class="card-content">
      <h2>Recipes</h2>
      <p>
        Recipes I've collected over the years. They're all vegan.
      </p>
    </div>
    
    <div class="card-links">
      <a href="/recipes/kale">Massaged Kale</a>
      <a href="/recipes/vegan-chicken-pie">Vegan Chicken Pie</a>
      <a href="/recipes/pizza-dough">Easy Pizza Dough</a>
    </div>
  </section>
</div>

<style>
  .sections {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .card {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 2rem;
    padding: 2rem;
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  .card h2 {
    font-family: 'Libre Caslon Display', serif;
    font-size: 1.8rem;
    margin-bottom: 1rem;
  }

  .card p {
    font-family: 'Libre Caslon Text', serif;
    line-height: 1.6;
  }

  .card-links {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    justify-content: center;
  }

  .card-links a {
    display: inline-block;
    padding: 0.8rem 1.5rem;
    background: #f5f5f5;
    text-decoration: none;
    color: inherit;
    border-radius: 4px;
    font-family: 'Libre Caslon Text', serif;
    transition: background 0.2s;
  }

  .card-links a:hover {
    background: #e5e5e5;
  }

  @media (max-width: 768px) {
    .card {
      grid-template-columns: 1fr;
    }

    .card-links {
      flex-direction: row;
      flex-wrap: wrap;
    }
  }
</style>
