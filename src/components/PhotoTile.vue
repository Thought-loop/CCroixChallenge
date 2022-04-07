<template>
  <div class="tile">
      <!-- <img class="photo" v-bind:src=image.path v-on:click="showHideModal"/> -->
      <img class="photo" v-bind:src=image.path />
  </div>
</template>

<script>
export default {

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