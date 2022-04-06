<template>
  <div class = 'bar'>
      <img v-bind:src="logo" />
      <h3> Current Connection - Offline </h3>
      <h3> Photos - 100 </h3>
      <h3> Last Upload - 1/2/2022 4:21p </h3>
  </div>
</template>

<script>
import logo from "./img/logo.png"
export default {
    name: 'status-bar'
}
</script>

<style>

</style>