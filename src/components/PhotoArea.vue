<template>
    <div class = 'photo-container'>
        <h2>{{ title }}</h2>
        <div class = 'photo-container-photos'>
            <photo-tile v-for='image in images' v-bind:image="image" v-bind:key="image.id" />
        </div>
    </div>
</template>

<script>
import PhotoTile from './PhotoTile.vue'
export default {
  components: { PhotoTile },
  props: {
        areaTitle: String,
        photos: Array 
    },
    data(){
        return {
            title: this.areaTitle,
            images: this.photos
        }
    }

}
</script>

<style>
    .photo-container{
        margin: 4%;
    }

    .photo-container-photos{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        width: 100%;
    }


</style>