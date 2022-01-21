<script>
  import logo from "./assets/svelte.png";
  import Counter from "./lib/Counter.svelte";
  import Header from "./lib/Header.svelte";
  import PlayGrid from "./lib/PlayGrid.svelte";
</script>

<main>
  <div class="mainContainer">
    <Header />
    <PlayGrid />
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  .mainContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }
</style>
