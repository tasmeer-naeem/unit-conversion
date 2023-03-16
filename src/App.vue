<template>
 <div>
 <dashboard-page/>
 </div>
</template>

<script>
import DashboardPage from './pages/dashboardPage.vue'


export default {
  name: 'App',
  components: {
    DashboardPage 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
