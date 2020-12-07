<script>
  const random = 200 + Math.floor(Math.random() * 100)
  const src = `https://picsum.photos/${random}/${random}`

  let loading = true
</script>

<style>
  img {
    width: 200px;
    height: 200px;
    object-fit: cover;
  }

  .wrapper {
    width: 200px;
    height: 200px;
    position: relative;
  }

  .loader {
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 200px;
    height: 200px;
  }
</style>

<div class="wrapper">
  {#if loading}
    <div class="loader">Loading...</div>
  {/if}

  <img {src} alt="random" on:load={() => (loading = false)} />
</div>
