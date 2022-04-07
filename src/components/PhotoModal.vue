<template>
  <div class="modal">
      <div class="modal-content">
        <img class="modal-image" v-bind:src=image.path />
        <span class="modal-image-info">{{image.category}} | {{image.id}} | {{image.caption}}</span>
      </div>
  </div>
</template>

<script>
export default {
    name:'photo-modal',
    props: {
        image: Object
    },
}
</script>

<style>
.modal {
  display: block; 
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  height: 100vh;
  width: 100%;
  /* height: 65vw; Full height */
  overflow: clip; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.575); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
  display: flex;
  flex-direction: column;
  background-color: #fefefe;
  margin: 1% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  height: fit-content;
  max-width: fit-content; /* Could be more or less, depending on screen size */
}

.modal-image{
  object-fit: cover;
  min-height: 95vh;
  max-width: 90vw;
}

</style>