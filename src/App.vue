<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <componente3 />
  <hr>
  <componente2 />
  <hr>
  <HelloWorld msg="Mi primera aplicacion Vue.js"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import componente2 from './components/componente2.vue'
import componente3 from './components/componente3.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    componente2,
    componente3
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
.font-green {
  color: green;
}
</style>
