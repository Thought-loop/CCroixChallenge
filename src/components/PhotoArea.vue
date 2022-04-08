<template>
    <div class = 'photo-container'>
        <div class = 'photo-container-top-bar'>
            <h2 class = 'photo-container-top-bar-title'>{{ title }}</h2>
            <div class = 'photo-container-top-bar-control'>
                <h2 v-bind:style="{color: countColor}">{{numPhotos}} Photos</h2>
                <img v-bind:src=upIconURL v-on:click='expandRetract' v-if='expandArea' />
                <img v-bind:src=downIconURL v-on:click='expandRetract' v-if='!expandArea' />
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
    name: 'photo-area',
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
        },
        countColor(){
            if(this.title == 'Photos Not Associated'){
                return 'firebrick'
            }
            else{
                return 'green'
            }
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
        margin: 30px 5%;
        border-style: solid;
        background-color: rgba(105, 105, 105, 0.75);
    }

    .photo-container-top-bar{
        margin-inline: 1vw;
        display: flex;
        justify-content: space-between;
        font-size: 15px;

    }
    
    .photo-container-top-bar-control{
        display:flex;
        justify-content: right;
        flex-grow: .5;
    }

    .photo-container-photos{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        width: 100%;
    }



</style>