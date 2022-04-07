<template>
  <div class="photo-tile">
      <img class="photo-background" v-bind:src=image.path>
      <img class="photo" v-bind:src=image.path>
      
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
    .photo-tile{
        display: flex;
        border-style: solid;
        margin: 1rem;
        width: 10vw;
        height: 10vw;
        align-items: center;
        justify-content: center;
        background-size: 100%;
        backdrop-filter: blur(5px);
        position: relative;
        overflow: hidden;

    }
    
    .photo-tile>*{
        position: absolute;
    }
    
    .photo{
        max-height: 95%;
        max-width: 95%;
    }

    .photo-background{
        height: 100%;
        width: 100%;
        filter: blur(25px) grayscale(0%);
    }
</style>