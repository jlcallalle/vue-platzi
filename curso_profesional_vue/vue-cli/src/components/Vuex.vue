<template>
  <div class="container vuex">
    <!-- <p>Componente: Vuex.vue</p> -->
    <h2>Vuex</h2>
    <h2>Contador</h2>
    <p> {{ count }} {{ stringText }} </p>
    <button @click="increment"> + </button> 
    <button @click="decrement"> - </button>
  </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'Vuex',
  data () {
    return {
        test: 'test'
    }
  },
  /* computed : {
      count() {
          return this.$store.state.count
      }
  }, */
 /*  computed : mapState(['count']) */
  computed : {
      ...mapState(['count']),
      stringText() {
          return this.test
      }
  },
  methods: {
      /* increment() {
          this.$store.commit('increment')
      },
      decrement() {
          this.$store.commit('decrement')
      } */
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
