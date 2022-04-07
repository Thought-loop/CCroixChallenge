<template>
  <div class = 'bar'>
      <img class = 'bar-logo' v-bind:src="logo" />
      <div class = 'bar-status-area'>
          <div class = "bar-connection-status">
            <h3>Current Connection</h3>
            <h3>Offline</h3>
          </div>
          <div class = "bar-photo-count">
            <h3>Photos</h3>
            <h3>100</h3>
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
            logo: 'https://uxwing.com/wp-content/themes/uxwing/download/32-video-photography-multimedia/image-upload.png'
        }
    }
}
</script>

<style>
    .bar{
        display: flex;
        justify-content: space-between;
    }

    .bar-logo{
        height: 10rem;
    }

    .bar-status-area{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-areas: 
            "connection count"
            "upload upload";
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
</style>