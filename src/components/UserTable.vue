<template>
    <table>
      <!-- Table Header -->
      <thead>
        <tr>
          <th>Username</th>
          <th>Email</th>
          <th>Phone</th>
          <th>ID</th>
          <th>Creation Date</th>
        </tr>
      </thead>
      <!-- Table Body -->
      <tbody>
        <tr v-for="user in users" :key="user.id" @click="userClick(user)">
          <td>{{ user.username }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.phone }}</td>
          <td>{{ user.id }}</td>
          <td>{{ user.creationDate }}</td>
        </tr>
      </tbody>
    </table>
  </template>
  
  <script>
  export default {
    props: {
      users: Array,
    },
    methods: {
      userClick(user) {
        this.$emit("userClick", user);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add some styling for the table */
  table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 1rem;
  }
  
  table, th, td {
    border: 1px solid #ddd;
  }
  
  th, td {
    padding: 8px;
    text-align: left;
  }
  
  th {
    background-color: #f2f2f2;
  }
  </style>
  