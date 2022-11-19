<script lang="ts">
  export let img: string;
</script>

<div id="backdrop-container">
  <picture id="background-landscape">
    <source type="image/avif" srcset="/img/{img}-landscape.avif" />
    <source type="image/webp" srcset="/img/{img}-landscape.webp" />
    <img src="/static/{img}-landscape.jpg" alt="Anna és Marca" />
  </picture>
  <picture id="background-portrait">
    <source type="image/avif" srcset="/img/{img}-portrait.avif" />
    <source type="image/webp" srcset="/img/{img}-portrait.webp" />
    <img src="/static/{img}-portrait.jpg" alt="Anna és Marca" />
  </picture>
</div>

<style>
  :global(body) {
    margin: 0;
    background-color: black;
  }

  #backdrop-container {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
  }

  picture {
    width: 100%;
    height: 100%;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  @media (min-aspect-ratio: 1/1) {
    #background-portrait {
      display: none;
    }
  }

  @media (max-aspect-ratio: 1/1) {
    #background-landscape {
      display: none;
    }
  }
</style>
