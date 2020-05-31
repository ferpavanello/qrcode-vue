<template>
  <div id="app">
    <Generator msg="QRCode Generator" />
  </div>
</template>

<script>
import Generator from './components/Generator.vue'

export default {
  name: 'App',
  components: {
    Generator
  }
}
</script>

<style>
body {
  margin: 0;
  background: linear-gradient(90deg, rgba(60,129,213,1) 0%, rgba(75,75,185,1) 50%, rgba(24,18,126,1) 100%);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  color: #000;
}
</style>
