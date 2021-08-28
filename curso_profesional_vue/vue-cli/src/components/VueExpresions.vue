<template>
  <div class="hello">
    <p>Componente: VueExpresions.vue</p>
    <h2>Expresiones</h2>
    <p> {{ welcome }}</p>
    <p>{{ 1 + 1 }}</p>
    <p>{{ 'Hola' + ' Mundo'}}</p>
    <p>{{ true ? true : false }}</p>
    <p>{{ person.name }}</p>
    <p>{{ person.name.toUpperCase() }}</p>
    <p>{{ JSON.stringify(person)}}</p> 
  </div>
</template>

<script>
export default {
  name: 'VueExpresions',
  data () {
    return {
      welcome: 'Hola Vue.js',
      person: {
          name: 'jorge'
      },
    }
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
