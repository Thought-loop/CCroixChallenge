<template>
  <div id="app">
      <status-bar />
      <photo-modal v-bind:image='currentModalImage' v-if="displayModal" v-on:click="toggleModal" />
      <photo-area v-bind:areaTitle="notAsscTitle" v-bind:photos="photoRange(1,54)" v-bind:expanded="false" @show-modal="showModal"/>
      <photo-area v-bind:areaTitle="uploadTitle" v-bind:photos="photoRange(55,146)" v-bind:expanded="true" @show-modal="showModal"/>
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
            uploadTitle: 'Photos to upload',
            notAsscTitle: 'Photos not associated',
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
  
  padding: 1vh;
  min-height: 94vh;

  background-image: url("https://c.pxhere.com/images/8c/78/40e243d8510805a3abc997d0e3b7-1433401.jpg!d");
  background-attachment: fixed;
  background-size: 100%;

}

@media only screen and (max-width: 1000px) {
        .photo-tile{
            width: 25vw;
            height: 25vw;
            margin: 5px 0%;
        }

        .photo-container{
          margin: 30px 0%;
        }
    }
</style>
