<template>
    <div>
      <h3>User Report</h3>
      <p>Username: {{ user.username }}</p>
      <p>Email: {{ user.email }}</p>
      <p>Phone: {{ user.phone }}</p>
      <!-- Add other user details as needed -->
      <button @click="generateReport">Generate Report</button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      user: Object,
    },
    methods: {
      generateReport() {
        this.$emit("generateReport");
      },
    },
  };
  </script>
  
  <style scoped>
  /* Style the UserPopup */
  div {
    border: 1px solid #ddd;
    padding: 1rem;
    margin: 1rem 0;
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
  