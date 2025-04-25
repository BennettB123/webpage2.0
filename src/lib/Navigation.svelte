<script lang="ts">
  import { page } from '$app/stores';
</script>

<nav>
  <ul class="nav-links">
    <li class:active={$page.url.pathname === '/about-me' || $page.url.pathname === '/'}>
      <a href="/about-me">About Me</a>
    </li>
    <li class:active={$page.url.pathname === '/projects'}>
      <a href="/projects">Projects</a>
    </li>
  </ul>
</nav>

<style>
  nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #313131;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .nav-links {
    display: flex;
    list-style: none;
    gap: 2rem;
    margin: 0;
    padding: 0;
  }

  .nav-links a {
    text-decoration: none;
    color: #e0e0e0;
    font-weight: 500;
    transition: color 0.3s ease;
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
