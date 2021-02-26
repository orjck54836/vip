<template>
  <div id="app">
    <index msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import index from './components/index.vue'

export default {
  name: 'App',
  components: {
    index
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
}
@import "./assets/all.scss";
</style>
