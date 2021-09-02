<template>
  <div class="container integra" v-show="mostrarSection">
      <!-- <p>Componente: VueIntegra.vue</p> -->
      <section class="section">
        <nav class="nav has-shadow">
            <div class="container">
                <div class="field has-addons">
                    <div class="control"><input class="input is-large" type="text" placeholder="¿Qué canción estás buscando?" v-model="searchQuery" /></div>
                    <div class="control"><a class="button is-info is-large" v-on:click="search">Buscar</a></div>
                    <div class="control"><a class="button is-danger is-large">&times;</a></div>
                </div>
                <p class="help is-info has-text-right"><small>{{ searchMessage }}</small></p>
            </div>
        </nav>
        <div class="container results">
            <div class="columns">
                <div class="column" v-for="t in tracks" :key="t.id">{{ t.name }} - {{ t.artist }}</div>
            </div>
        </div>
    </section>
    <br>
    {{ info }}
    <br>
    <br>
    <h1>Listado de Precio de Bitcoin</h1>
    <div v-for="currency in info" :key="currency.id">
        {{ currency.description }}:
        <span class="lighten">
        <span v-html="currency.symbol"></span>{{ currency.rate_float}}
        </span>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

const tracks = [
  { name: 'Muchacha', artist: 'Luis Alberto Spinetta' },
  { name: 'Hoy aca en el baile', artist: 'El Pepo' },
  { name: 'I was made for loving you', artist: 'Kiss' }
]

export default {
  name: 'VueIntegra',
  data () {
    return {
      searchQuery: '',
      tracks: [],
      info: null,
      mostrarSection: false,
    }
  },
  computed: {
    searchMessage () {
      return `Encontrados: ${this.tracks.length}`
    }
  },
  methods: {
    search () {
      this.tracks = tracks
    }
  },
  mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response.data.bpi))
      /* .then(response => (this.info = response)) */
      .catch(error => console.log(error))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css";
h3 {
  margin: 40px 0 0;
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
