<template>
  <div id="app">
    <ApiPosts msg="Get posts by api"/>
  </div>
</template>

<script>
import ApiPosts from './components/ApiPosts.vue'

export default {
  name: 'App',
  components: {
    ApiPosts
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
