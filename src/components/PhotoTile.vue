<template>
  <div class="tile">
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
            smileyURL: 'https://m.media-amazon.com/images/I/51zLZbEVSTL._AC_SX466_.jpg',
            picUrl : 'https://www.thought-loop.com/pic1.jpg'
        }
    }
}
</script>

<style>
    .photo{
        
        height: 10rem;
    }
</style>