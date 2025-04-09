<script lang="ts">
  // Projects page
</script>

<main>
  <h1>My Projects</h1>
  
  <div class="content">
    <div class="intro">
      <p>
        Here's a collection of projects I've worked on. Each one represents different skills
        and technologies I've learned throughout my development journey.
      </p>
    </div>
    
    <div class="project-list">
      <div class="project-card">
        <h2>Project 1</h2>
        <p class="tech-stack">Tech stack: HTML, CSS, JavaScript, Svelte</p>
        <p class="description">
          A detailed description of your first project. What problem did it solve?
          What technologies did you use? What did you learn?
        </p>
        <div class="project-links">
          <a href="#" target="_blank" rel="noopener noreferrer">Live Demo</a>
          <a href="#" target="_blank" rel="noopener noreferrer">GitHub</a>
        </div>
      </div>

      <div class="project-card">
        <h2>Project 2</h2>
        <p class="tech-stack">Tech stack: [Technologies used]</p>
        <p class="description">
          A detailed description of your second project. What problem did it solve?
          What technologies did you use? What did you learn?
        </p>
        <div class="project-links">
          <a href="#" target="_blank" rel="noopener noreferrer">Live Demo</a>
          <a href="#" target="_blank" rel="noopener noreferrer">GitHub</a>
        </div>
      </div>
      
      <div class="project-card">
        <h2>Project 3</h2>
        <p class="tech-stack">Tech stack: [Technologies used]</p>
        <p class="description">
          A detailed description of your third project. What problem did it solve?
          What technologies did you use? What did you learn?
        </p>
        <div class="project-links">
          <a href="#" target="_blank" rel="noopener noreferrer">Live Demo</a>
          <a href="#" target="_blank" rel="noopener noreferrer">GitHub</a>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
  .content {
    max-width: 1000px;
    margin: 0 auto;
  }
  
  h1 {
    font-size: 2.5em;
    margin-bottom: 1em;
  }
  
  .intro {
    margin-bottom: 2em;
  }
  
  .project-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .project-card {
    background-color: #f9f9f9;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.15);
  }
  
  .project-card h2 {
    color: #ff3e00;
    margin-top: 0;
  }
  
  .tech-stack {
    color: #666;
    font-style: italic;
    margin-bottom: 1rem;
  }
  
  .project-links {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
  }
  
  .project-links a {
    color: #ff3e00;
    text-decoration: none;
    font-weight: bold;
  }
  
  .project-links a:hover {
    text-decoration: underline;
  }
  
  @media (max-width: 768px) {
    .project-list {
      grid-template-columns: 1fr;
    }
  }
</style>