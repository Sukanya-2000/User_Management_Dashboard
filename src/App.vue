<template>
  <div id="app">
    <Dashboard />
  </div>
</template>

<script>
import Dashboard from "@/views/Dashboard.vue";

export default {
  components: {
    Dashboard,
  },
};
</script>

<style>
/* Add your global styling here */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}

#app {
  background-color: #fff;
  margin: 1rem;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
