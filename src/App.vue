<template>
  <div id="app">
      <status-bar />
      <photo-area v-bind:areaTitle="notAsscTitle" v-bind:photos="photoRange(1,100)" v-bind:expanded="false" @show-modal="showModal"/>
      <photo-area v-bind:areaTitle="uploadTitle" v-bind:photos="photoRange(101,146)" v-bind:expanded="true"/>
      <photo-modal v-bind:image='currentModalImage' v-if="displayModal" v-on:click="toggleModal" />
  </div>
</template>

<script>
import PhotoArea from './components/PhotoArea.vue'
import PhotoModal from './components/PhotoModal.vue'
import StatusBar from './components/StatusBar.vue'


export default {
  name: 'App',
  components: {
    StatusBar,
    PhotoArea,
    PhotoModal
  },
  data(){

    return{
            uploadTitle: 'Photos to Upload',
            notAsscTitle: 'Photos not Associated',
            currentModalImage: null,
            displayModal: false
        }
    },
  methods: {
    photoRange(min, max){
      let photos = [];
      for (let i = min-1; i <= max-1; i++) {
        photos.push(this.$store.state.images[i]);
      }
      return photos;
    },
    showModal(image){
      this.currentModalImage=image;
      this.displayModal = true;
    },
    toggleModal(){
      this.displayModal = !this.displayModal;
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
