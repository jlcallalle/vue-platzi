<template>
  <div id="app">
     <img src="./assets/logo.png">
     <h1>{{ msg }}</h1>
      <div class="contenido" v-show="mostrarContenido"> <!-- display none-->
        <p>{{ 1 + 1 }}</p>
        <p>{{ 'Hola' + 'Mundo'}}</p>
        <p>{{ true ? true : false }}</p>
        <p>{{ person.name }}</p>
        <p>{{ person.name.toUpperCase() }}</p>|
        <p>{{ JSON.stringify(person)}}</p>  
        <p>{{ true ? 'true' : 'false'}}</p>
      </div>
    <p v-if="showValue"> {{ value }}</p>
    <p v-else> {{ 'algo más' }}</p>
    
    <ul>
    <li v-for="item in items" :key="item">
      {{ item.mensaje }}
    </li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hola Vue.js',
      person: {
          name: 'juan'
      },
      mostrarContenido: false,
      showValue: false,
      value : 'algo',
       items: [
        { mensaje: 'Foo' },
        { mensaje: 'Bar' }
      ]
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
