<script lang="ts">
  import profilePic from '../assets/ProfilePic.jpg';
</script>

<main>
  <h1>About Me</h1>
  
  <div class="content">
    <div class="profile-image">
      <img src={profilePic} alt="Me" />
    </div>
    <div class="bio-text">
      <h2>Hello, I'm Bennett Ballentine</h2>
      <p>
        I'm a passionate software developer primarily focusing on the backend.
        This is my personal webpage to showcase my programming journey and the projects I've worked on throughout the years.
      </p>
    </div>
  </div>
</main>

<style>
  .content {
    max-width: 800px;
    margin: 0 auto;
    text-align: left;
    font-size: 1.2rem;
    margin-bottom: 2em;
    display: flex;
    align-items: flex-start;
    gap: 2rem;
  }
  
  h1 {
    font-size: 2.5em;
    margin-bottom: 1em;
  }
  
  h2 {
    color: #ff3e00;
    margin-top: 1.5em;
    font-size: 2rem;
  }
  
  .profile-image {
    flex-shrink: 0;
  }
  
  .profile-image img {
    width: 200px;
    height: auto;
    border-radius: 50%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    border: 2px solid #ff3e00;
  }
  
  .bio-text {
    flex-grow: 1;
  }
  
  p {
    line-height: 1.6;
  }
  
  @media (max-width: 768px) {
    .bio-content {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    
    .profile-image {
      margin-bottom: 1.5rem;
    }
  }
</style>