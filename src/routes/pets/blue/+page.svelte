<script>
    import blueImage from './Blue.jpeg';
  </script>
  
  <svelte:head>
    <title>Blue</title>
    <meta name="description" content="Meet Blue, the gentle Bluetick Coonhound rescue dog. Despite being shy and afraid of kitchen floors, she was a great protector with her loud howls." />
  </svelte:head>
  
  <section class="container">

    <h1 class="name">Blue</h1>
    <div class="flex_wrapper">
      <div class="image-container">
        <img src={blueImage} alt="Blue the bluetick coonhound">
      </div>
      <div class="content-section">
        <div class="content">
          <h2>About Blue</h2>
          <p>
            Blue is a Bluetick Coonhound that I took in from my sister. Blue had a lot of energy as a puppy and wasn't a good fit for them. I remember driving her back to Philadelphia and her vomiting all over the car, trouble right from the start. She made her mark around the house, chewing up various things. She was always a gentle sweet dog though. She was afraid of the kitchen and the wood floors. 
          </p>
          <p>
            Even though Blue was a sweet shy dog she did a great job of protecting our house. She was a loud howler and kept a close eye out the windows. One day I returned home from work and found the ladder I had been using to set the climbing wall propt up under the window. I can only assume the would be burgler was scared off by Blue's howls.
          </p>
        </div>
      </div>
    </div>
  </section>

  <style>
    /* Pet-specific styles */
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

    .content-section {
      grid-column: 2 / 3;
      grid-row: 1 / 2;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      height: 100%;
    }

    .content {
      flex: 1;
    }

    .content h2 {
      font-family: 'Libre Caslon Display', serif;
      font-size: 1.8rem;
      margin-bottom: 1rem;
    }

    .content p {
      font-family: 'Libre Caslon Text', serif;
      line-height: 1.6;
      margin-bottom: 1rem;
    }

    @media (max-width: 768px) {
      .flex_wrapper {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto;
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

      .content-section {
        grid-column: 1 / 2;
        grid-row: 2 / 3;
        height: auto;
      }
    }
  </style>
  