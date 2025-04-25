<script lang="ts">
  import '../app.css';
  import Navigation from "../lib/Navigation.svelte";
  import TitleBar from "../lib/TitleBar.svelte";
</script>

<TitleBar />
<Navigation />

<main>
  <slot />
</main>

<style>
  main {
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }
</style>
