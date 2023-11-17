<template>
    <div>
      <h2>User Details</h2>
      <input v-model="searchQuery" placeholder="Search users..." />
      <UserTable :users="filteredUsers" @userClick="openUserPopup" />
      <UserPopup v-if="selectedUser" :user="selectedUser" @generateReport="generateReport" />
    </div>
  </template>
  
  <script>
  import UserTable from "@/components/UserTable.vue";
  import UserPopup from "@/components/UserPopup.vue";
  
  export default {
    components: {
      UserTable,
      UserPopup,
    },
    data() {
      return {
        users: [
          { id: 1, username: "user1", email: "user1@example.com", phone: "1234567990", creationDate: "2023-01-01" },
          { id: 1, username: "user2", email: "user2@example.com", phone: "1234567880", creationDate: "2023-01-02" },
          { id: 1, username: "user3", email: "user3@example.com", phone: "1234567790", creationDate: "2023-03-01" },
          { id: 1, username: "user4", email: "user4@example.com", phone: "1234566890", creationDate: "2023-01-04" },
          { id: 1, username: "user5", email: "user5@example.com", phone: "1234557890", creationDate: "2023-05-01" }

          // Add more user data
        ],
        selectedUser: null,
        searchQuery: "",
      };
    },
    computed: {
      filteredUsers() {
        return this.users.filter((user) =>
          user.username.toLowerCase().includes(this.searchQuery.toLowerCase())
        );
      },
    },
    methods: {
      openUserPopup(user) {
        this.selectedUser = user;
      },
      generateReport() {
        // Implement report generation logic
        console.log("Generating report for user:", this.selectedUser);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add some styling for better aesthetics */
  input {
    margin-bottom: 1rem;
    padding: 0.5rem;
    font-size: 1rem;
  }
  
  /* Style the table */
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
  