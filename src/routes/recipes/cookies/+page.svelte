<script>
  import cookieImage from './Cookie.jpeg';
</script>

<svelte:head>
  <title>Vegan Chocolate Chip Cookies</title>
  <meta name="description" content="Delicious vegan chocolate chip cookies recipe using Earth Balance butter and soy milk. Perfect for vegan baking with detailed instructions." />
</svelte:head>

<section class="container">

  <h1 class="name">Vegan Chocolate Chip Cookies</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={cookieImage} alt="Vegan Peanut Butter Chip Cookie">
    </div>
    <div class="ingredients-section">
      <div class="ingredients">
        <h2>Ingredients</h2>
        <ul>
          <li>½ cup butter (Earth Balance)</li>
          <li>1 cup brown sugar</li>
          <li>¼ cup soy milk</li>
          <li>2 cups all purpose flour</li>
          <li>1 Tbsp vanilla extract</li>
          <li>1 tsp baking powder</li>
          <li>1 tsp baking soda</li>
          <li>2 tsp cornstarch</li>
          <li>½ tsp salt</li>
          <li>1 cup chocolate chunks</li>
        </ul>
      </div>
    </div>
    <div class="instructions two_column">
      <h2>Instructions</h2>
      <ol>
        <li>Preheat oven to 350°F</li>
        <li>Cream butter and sugar together in electric mixer</li>
        <li>Add soy milk and vanilla, mix to combine</li>
        <li>Add flour, baking powder, baking soda, cornstarch, and salt - mix until combined</li>
        <li>
          Check dough consistency - it should be thick but holdable. Add small amounts of soy milk
          if too dry, or flour if too wet
        </li>
        <li>Fold in chocolate chunks</li>
        <li>Roll into balls and place on parchment-lined baking tray</li>
        <li>Bake 13-15 minutes until edges are lightly golden (check at 11 minutes)</li>
        <li>Let cool on wire rack</li>
      </ol>
      <p class="note">Makes approximately 12 cookies</p>
    </div>
  </div>
</section>

<style>
  /* Recipe-specific styles */
  .two_column {
    grid-column: 1 / -1;
  }

  .name {
    margin-bottom: 2rem;
  }

  .flex_wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr;
    gap: 1.5rem;
    align-items: start;
  }

  .image-container {
    grid-column: 1 / 2;
    grid-row: 1 / 2;
    height: 100%;
    display: flex;
    align-items: stretch;
  }

  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px;
  }

  .ingredients-section {
    grid-column: 2 / 3;
    grid-row: 1 / 2;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    height: 100%;
  }

  .ingredients {
    flex: 1;
  }

  .instructions.two_column {
    grid-column: 1 / -1;
    grid-row: 2 / 3;
    margin-top: 1.5rem;
  }

  @media (max-width: 768px) {
    .flex_wrapper {
      grid-template-columns: 1fr;
      grid-template-rows: auto auto auto;
      gap: 1rem;
    }

    .image-container {
      grid-column: 1 / 2;
      grid-row: 1 / 2;
      height: auto;
    }

    .image-container img {
      max-height: 300px;
      object-fit: cover;
    }

    .ingredients-section {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      height: auto;
    }

    .instructions.two_column {
      grid-column: 1 / 2;
      grid-row: 3 / 4;
      margin-top: 1rem;
    }
  }
</style>
