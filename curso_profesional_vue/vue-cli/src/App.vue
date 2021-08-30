<template>
  <div id="app">
    <!-- <img class="logo-vue" alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld msg="Vue CLI template base"/>
    <vueExpresions />
    <vueIntegra />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import VueExpresions from './components/VueExpresions.vue'
import VueIntegra from './components/VueIntegra.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, VueExpresions, VueIntegra
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  padding: 10px 20px;
  /* margin-top: 60px; */
}
.logo-vue {
  position: absolute;
  top:0;
  left: 0;
}
h3, h4 {
  margin: 10px 0;
}
p {
  margin: 6px 0 8px 0;
}
</style>
