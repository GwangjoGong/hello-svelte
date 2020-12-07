<script>
  import RandomImage from './components/RandomImage.svelte'
  let count = 6
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .gallery {
    margin: 0 auto;
    margin-top: 50px;
    display: grid;
    gap: 10px;
    grid-template-columns: repeat(3, 200px);
    grid-auto-rows: 200px;
  }

  .add-picture {
    float: right;
    background-color: #ff3e00;
    color: white;
    border-radius: 5px;
    border: none;
    padding: 10px;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Svelte Gallery</h1>
  <button
    class="add-picture"
    on:click={() => {
      count += 1
    }}>New Picture</button>
  <div class="gallery">
    {#each Array(count) as _, i}
      <RandomImage />
    {/each}
  </div>
</main>
