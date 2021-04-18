<template>
  <div id="app">
      <navbar />
      <HelloWorld />
      <listinfo />
 
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import navbar from './components/navbar'
import Navbar from './components/navbar.vue'
import listinfo from './components/listinfo'
import Listinfo from './components/listinfo.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    navbar,
    Navbar,
    listinfo,
    Listinfo
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
  
}
</style>
