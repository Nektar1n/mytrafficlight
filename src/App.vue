<template>
  <div id="app">
    <router-link to="/red">Red</router-link>
    <router-link to="/yellow">Yellow</router-link>
    <router-link to="/green">Green</router-link>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 72px;
}
</style>
