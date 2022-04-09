<template>
  <div class = 'bar'>
      <img class = 'bar-logo' v-bind:src="logo" />
      <div class = 'bar-status-area'>
          <div class = "bar-connection-status">
            <h3>Current Connection</h3>
            <h3 class="caution-text">Offline</h3>
          </div>
          <div class = "bar-photo-count">
            <h3>Photos</h3>
            <h3 class="caution-text">{{numPhotos}}</h3>
          </div>
          <div class = "bar-upload-info">
            <h3>Last upload xx/xx/xxxx x:xx</h3>
          </div>
      </div>
  </div>
</template>

<script>

export default {
    name: 'status-bar',
    data(){
        return{
            logo: 'https://www.protolabs.com/media/5cfh34gx/pl_icon_1_upload_cad.svg'
        }
    },
    props: {
        numPhotos: Number
    }
}
</script>

<style>
    .bar{
        display: flex;
        justify-content: space-between;
        margin-inline: 5%;
    }

    .bar-logo{
        padding-top: 1%;
        max-height: 15vh;
        max-width: 15vw;
        /* min-width: 10vw; */
    }

    .bar-status-area{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-areas: 
            "connection count"
            "upload upload";
        padding-top: 2%
    }

    .bar-status-area h3{
        margin: 3px;
    }

    .bar-connection-status{
        grid-area: connection;
    }

    .bar-photo-count{
        grid-area: count;
    }

    .bar-upload-info{
        grid-area: upload;
    }

    .caution-text{
        color: firebrick;
    }
</style>