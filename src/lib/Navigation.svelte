<script lang="ts">
  import { onMount } from "svelte";

  let currentPath = window.location.pathname;

  // Custom navigation function that prevents page refresh
  function navigate(event: MouseEvent, path: string) {
    event.preventDefault();

    // Only update if we're navigating to a different path
    if (path !== currentPath) {
      // Update browser history without refreshing
      window.history.pushState({}, "", path);

      // Update current path
      currentPath = path;

      // Dispatch a custom event to notify App.svelte of navigation
      window.dispatchEvent(new CustomEvent("routechange"));
    }
  }

  // Update current path when navigation happens using browser back/forward
  function updateCurrentPath() {
    currentPath = window.location.pathname;
  }

  onMount(() => {
    // Ensure current path is accurate on component mount
    currentPath = window.location.pathname;
  });
</script>

<svelte:window on:popstate={updateCurrentPath} />

<nav>
  <ul class="nav-links">
    <li
      class:active={currentPath === "/" ||
        currentPath === "" ||
        currentPath === "/about"}
    >
      <a href="/" on:click={(e) => navigate(e, "/")}>About Me</a>
    </li>
    <li class:active={currentPath === "/projects"}>
      <a href="/projects" on:click={(e) => navigate(e, "/projects")}>Projects</a
      >
    </li>
  </ul>
</nav>

<style>
  nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: .5rem;
    background-color: #313131;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .nav-links {
    display: flex;
    list-style: none;
    gap: 3rem;
    margin: 0;
    padding: 0;
  }

  .nav-links a {
    text-decoration: none;
    color: #e0e0e0;
    font-weight: 500;
    transition: color 0.3s ease;
    font-size: 1.25rem;
  }

  .nav-links a:hover {
    color: #ff3e00;
  }

  li.active a {
    color: #ff3e00;
    font-weight: bold;
  }

  @media (max-width: 600px) {
    nav {
      padding: 1rem;
    }

    .nav-links {
      gap: 1rem;
    }
  }
</style>
