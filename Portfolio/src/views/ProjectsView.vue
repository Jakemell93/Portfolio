<template>
    <section>
      <h2>My Projects</h2>
      <div class="project-grid">
        <ProjectCard
          v-for="(project, index) in projects"
          :key="index"
          :title="project.title"
          :description="project.description"
          :image="project.image"
          :link="project.link"
        />
      </div>
    </section>
  </template>
  
  <script>
  import ProjectCard from '../components/ProjectCard.vue'
  
  export default {
    name: 'ProjectsView',
    components: {
      ProjectCard,
    },
    data() {
      return {
        projects: [
          {
            title: 'Portfolio Sample',
            description: 'A sample project for demonstration.',
            image: 'path/to/image.jpg',
            link: 'https://example.com',
          },
          {
            title: 'Another Project',
            description: 'Another sample in Vue.',
            image: 'path/to/image2.jpg',
            link: 'https://example2.com',
          },
          // ... add more projects ...
        ],
      }
    },
  }
  </script>
  