<script lang="ts">
  // TitleBar component to display site name
</script>

<div class="site-title">
  <a href="/" on:click={(e) => {
    e.preventDefault();
    // Update browser history without refreshing
    window.history.pushState({}, '', '/');
    
    // Dispatch a custom event to notify App.svelte of navigation
    window.dispatchEvent(new CustomEvent('routechange'));
  }}>bennettcodes.com</a>
</div>

<style>
  .site-title {
    margin-bottom: 0.75rem;
    text-align: center;
  }
  
  .site-title a {
    font-size: 1.75rem;
    font-weight: bold;
    color: #ff3e00;
    text-decoration: none;
  }
</style>