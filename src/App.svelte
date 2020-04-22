<script>
  import { onMount } from "svelte/internal";
  import Game from "./game-src/game.ts";
  let canvas;
  onMount(async () => {
    let game = new Game(canvas);
    game.setup();
    game.run();
  });
</script>

<style>
  main {
    width: 100vw;
    height: 100vh;
    padding: 0;
    margin: 0;
  }
  canvas {
    width: 100%;
    height: 100%;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <canvas bind:this={canvas} id="app" />
</main>
