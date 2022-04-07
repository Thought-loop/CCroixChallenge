<template>
  <div class="tile">
      <img class="photo" v-bind:src=smileyURL />
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
            smileyURL: 'https://m.media-amazon.com/images/I/51zLZbEVSTL._AC_SX466_.jpg'
        }
    }
}
</script>

<style>
    .photo{
        width: 10rem;
    }
</style>