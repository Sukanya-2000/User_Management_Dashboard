<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>Dashboard</h1>
    <nav>
      <button @click="activeTab = 'userDetails'" :class="{ 'active': activeTab === 'userDetails' }">User Details</button>
      <button @click="activeTab = 'accountCreation'" :class="{ 'active': activeTab === 'accountCreation' }">Account Creation</button>
    </nav>
    <div v-show="activeTab === 'userDetails'">
      <UserDetails />
    </div>
    <div v-show="activeTab === 'accountCreation'">
      <AccountCreation />
    </div>
  </div>
</template>

<script>
import UserDetails from "@/components/UserDetails.vue";
import AccountCreation from "@/components/AccountCreation.vue";

export default {
  components: {
    UserDetails,
    AccountCreation,
  },
  data() {
    return {
      activeTab: 'userDetails',
    };
  },
};
</script>

<style>
/* Add some styling for the navigation */
nav {
  margin-bottom: 1rem;
}

button {
  background-color: #4CAF50;
  color: white;
  padding: 0.5rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-right: 1rem;
}

button.active {
  background-color: #45a049;
}
</style>
