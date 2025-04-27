<script lang="ts">
  export let project;
</script>

<div class="project-card">
  <h2>{project.name}</h2>
  <p class="project-year">{project.year}</p>
  <p class="tech-stack">Tech used: {project.techUsed.join(', ')}</p>
  <p class="description">{@html project.description}</p>

  {#if project.images && project.images.length > 0}
    <div class="project-images">
      {#each project.images as image}
        <img src={image} alt={project.name} />
      {/each}
    </div>
  {/if}

  <div class="project-links">
    {#if project.demoLink}
      <a href={project.demoLink} target="_blank" rel="noopener noreferrer">Live Demo</a>
    {/if}
    {#if project.githubLink}
      <a href={project.githubLink} target="_blank" rel="noopener noreferrer">GitHub</a>
    {/if}
  </div>

  {#if project.notes}
    <p class="notes"><strong>Note:</strong> {project.notes}</p>
  {/if}
</div>

<style>
  .project-card {
    background-color: #1a1a1a;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    transition:
      transform 0.2s ease,
      box-shadow 0.2s ease;
    border: 1px solid #333;
    width: 100%;
    box-sizing: border-box;
    min-width: 0;
  }
  .project-card:hover {
    transform: scale(105%);
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
    border-color: #ff3e00;
  }
  .project-card h2 {
    color: #ff3e00;
    margin-top: 0;
  }
  .project-year {
    color: #aaa;
    font-style: italic;
    margin-bottom: 1rem;
    text-align: center;
  }
  .tech-stack {
    color: #aaa;
    font-style: italic;
    margin-bottom: 1rem;
  }
  .project-images {
    margin: 1rem 0;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
  }
  .project-images img {
    width: 100%;
    max-width: 100%;
    height: auto;
    border-radius: 4px;
    object-fit: contain;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
  }
  .project-links {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
    justify-content: center;
  }
  .project-links a {
    color: #ff3e00;
    text-decoration: none;
    font-weight: bold;
    padding: 0.4rem 0.8rem;
    border-radius: 4px;
    background-color: rgba(255, 62, 0, 0.1);
    transition: all 0.2s ease;
  }
  .project-links a:hover {
    text-decoration: none;
    background-color: rgba(255, 62, 0, 0.2);
    transform: translateY(-2px);
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
  }
  .notes {
    margin-top: 1rem;
    font-size: 0.9em;
    border-left: 3px solid #ff3e00;
    padding-left: 10px;
    background-color: rgba(255, 62, 0, 0.1);
    padding: 0.5rem;
  }

  @media (max-width: 768px) {
    .project-card {
      padding: 1rem;
      font-size: 0.98em;
    }
  }

  @media (max-width: 480px) {
    .project-card {
      padding: 0.7rem;
      font-size: 0.93em;
    }
  }
</style>
