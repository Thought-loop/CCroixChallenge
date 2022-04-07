<template>
  <div id="app">
      <status-bar />
      <photo-area v-bind:areaTitle="notAsscTitle" v-bind:photos="photoRange(1,100)"/>
      <photo-area v-bind:areaTitle="uploadTitle" v-bind:photos="photoRange(101,146)"/>
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
  },
  data(){
        return{
            uploadTitle: 'Photos to Upload',
            notAsscTitle: 'Photos not Associated'
        }
    },
  methods: {
    photoRange(min, max){
      let photos = [];
      for (let i = min-1; i <= max-1; i++) {
        photos.push(this.$store.state.images[i]);
      }
      console.table(photos);
      return photos;
      // min=max;
      // return this.$store.state.images;
    }
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
