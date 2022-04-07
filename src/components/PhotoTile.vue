<template>
  <div class="tile">
      <img class="photo" v-bind:src=image.path v-on:click="showHideModal"/>
      <photo-modal v-bind:image='image' v-if="showModal" v-on:click="showHideModal"/>
  </div>
</template>

<script>
import PhotoModal from './PhotoModal.vue'
export default {
  components: { PhotoModal },
    name:'photo-tile',
    props: {
        image: Object

    },
    data(){
        return{
            showModal:false
        }
    },
    methods:{
        showHideModal(){
            this.showModal = !this.showModal;
        }
    }
}
</script>

<style>
    .photo{
        height: 10rem;
    }
</style>