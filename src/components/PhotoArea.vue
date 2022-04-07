<template>
    <div class = 'photo-container'>
        <div class = 'photo-container-top-bar'>
            <h2>{{ title }}</h2>
            <div class = 'photo-container-top-bar-control'>
                <h3>{{numPhotos}} Photos</h3>
                <img v-bind:src=upIconURL v-on:click='expandRetract' v-if='!expandArea' />
                <img v-bind:src=downIconURL v-on:click='expandRetract' v-if='expandArea' />
            </div>
            
        </div>
        <div class = 'photo-container-photos' v-if='expandArea'>
            <photo-tile v-for='image in selectedPhotos' v-bind:image="image" v-bind:key="image.id" v-on:click='$emit("show-modal",image)'/>
        </div>
    </div>
</template>

<script>
import PhotoTile from './PhotoTile.vue'
export default {
    name: 'photo-tile',
    emits: ['show-modal'],
    components: { PhotoTile },
  props: {
        areaTitle: String,
        photos: Array,
        expanded: Boolean 
    },
    data(){
        return {
            title: this.areaTitle,
            selectedPhotos: this.photos,
            expandArea: this.expanded,
            upIconURL: 'https://upload.wikimedia.org/wikipedia/commons/8/8d/Feather-arrows-chevron-up.svg',
            downIconURL: 'https://upload.wikimedia.org/wikipedia/commons/4/4b/Feather-arrows-chevron-down.svg'
        }
    },
    computed: {
        numPhotos(){
            return this.selectedPhotos.length;
        }
    },
    methods:{
        expandRetract(){
            this.expandArea = !this.expandArea;
        }
    }

}
</script>

<style>
    .photo-container{
        margin: 4%;
        border-style: solid;
    }

    .photo-container-top-bar{
        margin-inline: 5%;
        display: flex;
        justify-content: space-between;
    }

    .photo-container-top-bar-control{
        display:flex;
    }

    .photo-container-photos{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        width: 100%;
    }


</style>