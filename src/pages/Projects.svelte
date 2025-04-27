<script lang="ts">
  import { projectList } from "../lib/ProjectsList.svelte";
  import githubLogo from "../assets/githubLogo.svg";
  import ProjectCard from "../lib/ProjectCard.svelte";
</script>

<main>
  <h1>My Projects</h1>

  <div class="content">
    <div class="intro">
      <p>
        Here's a collection of projects developed in my free time. Each one
        represents different skills and technologies I've learned throughout my
        development journey. This is not an exhaustive list, but it gives a good
        overview of my work.
      </p>

      <a
        href="https://github.com/BennettB123"
        target="_blank"
        rel="noopener noreferrer"
        class="github-button"
      >
        <img src={githubLogo} alt="GitHub Logo" class="github-logo" />
        <span>Visit my GitHub</span>
      </a>
    </div>

    <div class="project-list">
      {#each projectList as project (project.name)}
        <ProjectCard {project} />
      {/each}
    </div>
  </div>
</main>

<style>
  .content {
    max-width: 1000px;
    margin: 0 auto;
    width: 100%;
    padding: 0 1rem;
    box-sizing: border-box;
  }

  .intro {
    margin: auto;
    font-size: 1.2em;
    max-width: 500px;
  }

  .github-button {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin: 1.5rem auto;
    padding: 0.6rem 1.2rem;
    background-color: #24292e;
    color: white;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    transition: all 0.2s ease;
    max-width: 200px;
  }

  .github-button:hover {
    background-color: #2f363d;
    transform: translateY(-2px);
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
  }

  .github-logo {
    width: 24px;
    height: 24px;
    filter: invert(1);
  }

  .project-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
    width: 100%;
  }

  @media (max-width: 768px) {
    .project-list {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
    .content {
      padding: 0 0.5rem;
    }
  }

  @media (max-width: 480px) {
    .content {
      padding: 0 0.2rem;
    }
  }
</style>
