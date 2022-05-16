<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :mensaje="mensaje"/>
    <Titulo titulo="Home Titulo editado"/>
    <Descripcion/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Titulo from './components/Titulo.vue'
import Descripcion from './components/Descripcion.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,Titulo,Descripcion
  },
  data(){
    return {
      mensaje: "este es un mensaje!"
    }
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
