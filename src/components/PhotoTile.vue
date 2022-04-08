<template>
  <div class = "photo-tile-and-text">
    <div class="photo-tile">
        <img class="photo" v-bind:src=image.path>
    </div>
    <div class = "photo-tile-text">
        <p>{{image.caption}}</p>
        <p>{{image.id}}</p>
        <p>{{image.category}}</p>
    </div>
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
        align-items: center;
        justify-content: center;
        position: relative;
        overflow: hidden;

        margin: 10px;
        width: 10vw;
        height: 10vw;

        border-style: solid;
        border-color:rgb(80, 84, 97);
        background-color: rgba(105, 105, 105, 0.486);

    }

    .photo-tile:hover{
        border-color:rgb(60, 63, 73);
        background-color: rgba(105, 105, 105, 0.658);
    }

    .photo-tile-text{
        display: flex;
        flex-direction: column;
    }

    .photo-tile-text p{
        margin: 0px;
    }
    
    
    .photo{
        max-height: 95%;
        max-width: 95%;
    }


</style>