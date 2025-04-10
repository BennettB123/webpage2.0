<script lang="ts">
  import { onMount } from "svelte";
  import { fly } from "svelte/transition";
  import Navigation from "./lib/Navigation.svelte";
  import TitleBar from "./lib/TitleBar.svelte";
  import AboutMe from "./pages/AboutMe.svelte";
  import Projects from "./pages/Projects.svelte";

  onMount(() => {
    handleRouteChange();
    window.addEventListener("popstate", handleRouteChange);
    window.addEventListener("routechange", handleRouteChange);

    return () => {
      window.removeEventListener("popstate", handleRouteChange);
      window.removeEventListener("routechange", handleRouteChange);
    };
  });

  // Transition configuration
  const flyOut = {
    x: 50,
    duration: 200,
  };

  const flyIn = {
    x: -50,
    delay: 200,
    duration: 200,
  };

  let currentPage = "about";
  handleRouteChange();

  function handleRouteChange() {
    const path = window.location.pathname;

    if (path === "/projects") {
      currentPage = "projects";
    } else {
      currentPage = "about";
    }
  }
</script>

<TitleBar />
<Navigation />

<main>
  {#key currentPage}
    <div in:fly={flyIn} out:fly={flyOut}>
      {#if currentPage === "about"}
        <AboutMe />
      {:else if currentPage === "projects"}
        <Projects />
      {/if}
    </div>
  {/key}
</main>

<style>
  main {
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }
</style>
