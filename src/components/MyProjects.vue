<template>
  <section id="MyProjects" class="projects-section">
    <h1>Projects</h1>
    <div class="projects-container">
      <div class="project-card" v-for="project in projects" :key="project.title">
        <div class="project-info">
          <h2>{{ project.title }}</h2>
          <p>{{ project.description }}</p>
          <div class="project-links">
            <!-- Only render the button if viewCodeLink has a value -->
            <a v-if="project.viewCodeLink" :href="project.viewCodeLink" target="_blank" class="view-code-link">View Code</a>
            <!-- Only render the button if detailsLink has a value -->
            <a v-if="project.detailsLink" :href="project.detailsLink" target="_blank" class="see-more-link">View Demo</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: 'Museum_AR',
          description: 'An Augmented Reality Android app using Flutter to view Smithsonian artifacts',
          viewCodeLink: '',
          detailsLink: 'https://youtube.com/shorts/6e0X06P0Skk?feature=share'
        },
        {
          title: 'Music Interval App',
          description: 'I developed an Android app using Java to assist in my piano exam preparation. The app generates random piano intervals, ranging from minor seconds to major ninths, and presents them for identification. Users can practice recognizing and accurately naming these intervals, helping them refine their interval recognition skills for the exam.',
          viewCodeLink: 'https://github.com/kevin224860/MusicIntervalApp'
        }
      ]
    };
  }
};
</script>

<style scoped>
.projects-section {
  padding: 150px 20px;
  background-color: #121212;
  color: #fff;
}

h1 {
  font-size: 36px;
  margin-bottom: 30px;
  text-align: left;
  color: var(--primary-color);
  border-bottom: 3px solid var(--primary-color);
  display: inline-block;
}

.projects-container {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  justify-content: center;
}

.project-card {
  background-color: #1e1e1e;
  border-radius: 15px;
  overflow: hidden;
  width: 350px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s;
}

.project-card:hover {
  transform: scale(1.05);
}

.project-info {
  padding: 15px;
}

.project-info h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.project-info p {
  font-size: 14px;
  color: #ccc;
  margin-bottom: 15px;
}

.project-links {
  display: flex;
  justify-content: space-between;
}

.view-code-link,
.see-more-link {
  padding: 8px 12px;
  color: #fff;
  text-decoration: none;
  border-radius: 8px;
  background-color: var(--primary-color);
  transition: background-color 0.3s;
}

.view-code-link:hover,
.see-more-link:hover {
  background-color: #6decb3;
  color: #000;
}

@media (max-width: 768px) {
  .projects-container {
    flex-direction: column;
    align-items: center;
  }

  .project-card {
    width: 100%;
  }
}
</style>
