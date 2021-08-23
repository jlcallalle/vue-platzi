<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <p>{{ 1 + 1 }}</p>
    <p>{{ 'Hola' + ' Mundo'}}</p>
    <p>{{ true ? true : false }}</p>
    <p>{{ person.name }}</p>
    <p>{{ person.name.toUpperCase() }}</p>
    <p>{{ JSON.stringify(person)}}</p> 
    
    <p v-if="showValue"> {{ value }}</p>
    <p v-else> {{ 'algo más' }}</p>
    <!-- <ul>
      <li v-for="item in items" :key="item">
        {{ item.mensaje }}
      </li>
    </ul> -->
    <input v-model="nombre" type="text">
    <button v-on:click="format">formatoNombre</button>
    <p>{{ formatoNombre }}</p>
    <br>
    <br>
    <section class="section">
      <input v-model="searchQuery" type="text">
      <button @click="search">Buscar</button>
      <ul v-for="t in tracks">
        <li >
          {{ t.name }} - {{ t.artist }} 
        </li>
      </ul>
      <p>{{ searchMessage }}</p>
    </section>
  </div>
</template>

<script>
const tracks = [
  { name: 'Muchacha', artist : 'Luis Alberto Spinetta'},
  { name: 'Hoy toca ser feliz', artist : 'Mago de Ozz'},
  { name: 'Luz de Luna', artist : 'Jorge'},
]
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hola Vue.js App',
      person: {
          name: 'juan'
      },
      showValue: true,
      value : 'algo',
      items: [
        { mensaje: 'Foo' },
        { mensaje: 'Bar' }
      ],
      nombre: '',
      formatoNombre: '',
      searchQuery: '',
      tracks: [],
    }
  },
  computed: {
    searchMessage () {
      return `Encontrados': ${this.tracks.length}`
    }
  },
  methods: {
    format() {
      this.formatoNombre = this.nombre.split(' ').join('-').toUpperCase()
    },
    search() {
      console.log(this.searchQuery);
      this.tracks= tracks
    },
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
