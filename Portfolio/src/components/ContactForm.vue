<template>
    <form @submit.prevent="submitForm">
      <label for="name">Name:</label>
      <input type="text" v-model="name" required />
  
      <label for="email">Email:</label>
      <input type="email" v-model="email" required />
  
      <label for="message">Message:</label>
      <textarea v-model="message" required></textarea>
  
      <button type="submit">Send</button>
    </form>
  </template>
  
  <script>
  export default {
    name: 'ContactForm',
    data() {
      return {
        name: '',
        email: '',
        message: '',
      }
    },
    methods: {
      submitForm() {
        // You could use an external API or a service like Formspree, Netlify forms, etc.
        console.log('Form submitted:', {
          name: this.name,
          email: this.email,
          message: this.message,
        })
        alert('Message sent (mock)!')
        this.name = ''
        this.email = ''
        this.message = ''
      },
    },
  }
  </script>
  
  <style scoped>
  /* Basic example, you can style it further */
  form {
    display: flex;
    flex-direction: column;
  }
  label {
    margin-top: 1rem;
  }
  button {
    margin-top: 1rem;
  }
  </style>
  