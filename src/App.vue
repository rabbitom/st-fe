<template>
  <div id="app">
    <URLForm/>
  </div>
</template>

<script>
import URLForm from './components/URLForm.vue'

export default {
  name: 'app',
  components: {
    URLForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
