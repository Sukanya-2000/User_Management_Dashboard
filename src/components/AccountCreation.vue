<template>
    <div>
      <h2>Account Creation</h2>
      <form @submit.prevent="submitForm">
        <label for="username">Username:</label>
        <input v-model="username" type="text" id="username" required />
  
        <label for="password">Password:</label>
        <input v-model="password" type="password" id="password" required />
  
        <button type="submit">Create Account</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        username: "",
        password: "",
      };
    },
    methods: {
      submitForm() {
        // Implement dummy request handling logic
        console.log("Form submitted with username:", this.username, "and password:", this.password);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add some styling for the form */
  form {
    max-width: 400px;
    margin: 0 auto;
  }
  
  label {
    display: block;
    margin-bottom: 0.5rem;
  }
  
  input {
    width: 100%;
    padding: 0.5rem;
    margin-bottom: 1rem;
  }
  
  button {
    background-color: #4CAF50;
    color: white;
    padding: 0.5rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  </style>
  