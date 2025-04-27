<script lang="ts">
</script>

<div class="site-title">
  <a
    href="/"
    on:click={(e) => {
      e.preventDefault();
      // Update browser history without refreshing
      window.history.pushState({}, "", "/");

      // Dispatch a custom event to notify App.svelte of navigation
      window.dispatchEvent(new CustomEvent("routechange"));
    }}>BennettCodes.com</a
  >
</div>

<style>
  .site-title {
    margin: 0.5rem;
    text-align: center;
  }

  .site-title a {
    font-size: 2rem;
    font-weight: bold;
    color: #ff3e00;
    text-decoration: none;
  }
</style>
