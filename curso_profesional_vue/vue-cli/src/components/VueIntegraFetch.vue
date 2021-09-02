<template>
  <div class="container integra" v-show="mostrarSection">
      <!-- <p>Componente: VueIntegraFetch.vue</p> -->
    <br>
    <h2>Lista Assets</h2>
    {{ assets }}
  </div>
</template>

<script>
import api from '@/api'


export default {
  name: 'VueIntegraFetch',
  data () {
    return {
      assets: [],
      mostrarSection: false,
    }
  },
  created() {
    api.getAssets()
    .then(assets => (this.assets = assets))
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
