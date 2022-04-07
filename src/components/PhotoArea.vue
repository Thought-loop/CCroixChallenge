<template>
    <div class = 'photo-container'>
        <photo-tile v-for='image in $store.state.images' v-bind:image="image" v-bind:key="image.id" />
    </div>
</template>

<script>
import PhotoTile from './PhotoTile.vue'
export default {
  components: { PhotoTile },

}
</script>

<style>
    .photo-container{
        display: flex;
        flex-wrap: wrap;
        width: 50%;
    }


</style>