<template>
    <section>
      <h2>Contact Me</h2>
      <ContactForm />
    </section>
  </template>
  
  <script>
import ContactForm from '../components/ContactForm.vue'

  
  export default {
    name: 'ContactView',
    components: {
      ContactForm,
    },
  }
  </script>
  