<template>
  <div id="app">
    <img class="logo-vue" alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Vue CLI template base"/>
    <vueExpresions />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import VueExpresions from './components/VueExpresions.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, VueExpresions
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
.logo-vue {
  position: absolute;
  top:0;
  left: 0;
}
</style>
