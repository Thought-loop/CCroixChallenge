<template>
  <div id="app">
      <status-bar v-bind:numPhotos="totalPhotos"/>
      <photo-modal v-bind:image='currentModalImage' v-if="displayModal" v-on:click="toggleModal" />
      <photo-area v-bind:areaTitle="notAsscTitle" v-bind:photos="photoRange(1,54)" v-bind:expanded="false" @show-modal="showModal"/>
      <photo-area v-bind:areaTitle="uploadTitle" v-bind:photos="photoRange(55,146)" v-bind:expanded="true" @show-modal="showModal"/>
      <upload-photo-buttons />
  </div>
</template>

<script>
import PhotoArea from './components/PhotoArea.vue'
import PhotoModal from './components/PhotoModal.vue'
import StatusBar from './components/StatusBar.vue'
import UploadPhotoButtons from './components/UploadPhotoButtons.vue'


export default {
  name: 'App',
  components: {
    StatusBar,
    PhotoArea,
    PhotoModal,
    UploadPhotoButtons
  },
  data(){

    return{
            uploadTitle: 'Photos Ready to Upload',
            notAsscTitle: 'Photos Not Associated',
            currentModalImage: null,
            displayModal: false
        }
    },
    computed: {
        totalPhotos(){
            return this.$store.state.images.length;
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

  user-select: none;
  
  padding: 1vh;
  min-height: 94vh;

  background-image: url("https://c.pxhere.com/images/8c/78/40e243d8510805a3abc997d0e3b7-1433401.jpg!d");
  background-attachment: fixed;
  background-size: 100%;

}

@media only screen and (max-width: 1000px) {
        .bar{
          margin: 0px;
        }

        .photo-tile{
            width: 25vw;
            height: 25vw;
            margin: 5px 0%;
        }

        .photo-container{
          margin: 30px 0%;
        }
    }

    @media only screen and (max-width: 800px) {
    
        .modal-content{
          padding: 10px;
        }
    }
    
    @media only screen and (max-width: 700px) {
        .bar{
          font-size: 12px;
        }

        .photo-container{
          margin: 15px 0%;
        }

        .modal{
          overflow:scroll;
        }
    }

    @media only screen and (max-width: 500px) {
       
       .action-button{
        width: 10rem;
        height: fit-content;
      } 

      .button-text{
        font-size:175%;
      }
    }

    
</style>
