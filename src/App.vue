<template>
  <div id="app">
    <img src="./assets/logo.png" class="app-img">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="stylus" scoped>
  #app 
    text-align center
</style>
