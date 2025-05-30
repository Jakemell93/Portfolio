<template>
    <div class="project-card">
      <img :src="image" :alt="title" />
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
      <a :href="link" target="_blank" rel="noopener">View Project</a>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProjectCard',
    props: {
      title: String,
      description: String,
      image: String,
      link: String,
    },
  }
  </script>
  
  <style scoped>
  .project-card {
    /* ... your styles ... */
  }
  </style>
  