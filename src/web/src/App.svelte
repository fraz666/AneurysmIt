<script lang="ts">
  import audioSrc from "./assets/audio.mp3";
  import imageSrc from "./assets/image.jpg";

  const audio = new Audio(audioSrc);

  let isZoomed = false;

  function playAnimation() {
    audio.play();
    isZoomed = !isZoomed;
  }
</script>

<main>
  <div class="meme" class:zoomed={isZoomed}>
    <button on:click={playAnimation}> Click me </button>
  </div>
</main>

<style>
  button {
    background-color: transparent;
    color: var(--primary);
    font-size: 18px;
    letter-spacing: 2px;
    text-transform: uppercase;
    display: inline-block;
    text-align: center;
    width: 10em;
    font-weight: bold;
    padding: 1em 0;
    border-radius: .25em;
    border: .15em solid;
    text-decoration: none;
    -webkit-transition: 1s all ease;
    transition: 1s ease all;
    
  }

  button:hover {
    background-color: var(--primary);
    color: #fff;
    border: .15em var(--primary);
  }

  .meme {
    display: flex;
    align-items: center;
    flex-direction: row;
    justify-content: center;

    background-image: url("assets/image.jpg");
    background-position: center;
    background-size: contain;
    height: 100vh;
    width: 100vw;
    transition: transform 2s;
  }

  .zoomed {
    transform: scale(1.3);
  }
</style>
