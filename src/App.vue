<template>
  <div id="app">
      <status-bar />
      <photo-area />
  </div>
</template>

<script>
import PhotoArea from './components/PhotoArea.vue'
import StatusBar from './components/StatusBar.vue'


export default {
  name: 'App',
  components: {
    StatusBar,
    PhotoArea
    
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
