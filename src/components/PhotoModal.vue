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
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  height: 100vh;
  width: 100%;
  overflow: clip;
  background-color: rgba(0, 0, 0, 0.575);
}

/* Modal Content/Box */
.modal-content {
  display: flex;
  flex-direction: column;
  background-color: #fefefe;
  margin: 1% auto;
  padding: 20px;
  border: 1px solid #888;
  /* max-height: 95vh; */
  height: 90%;
  max-width: fit-content;
}

.modal-image{
  object-fit: cover;
  height: 100%;
  /* max-height: 95vh;
  max-width: 90vw; */
}

</style>