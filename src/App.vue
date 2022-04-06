<template>
  <div id="app">
      <status-bar />
  </div>
</template>

<script>
import StatusBar from './components/StatusBar.vue'


export default {
  name: 'App',
  components: {
    StatusBar
    
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
