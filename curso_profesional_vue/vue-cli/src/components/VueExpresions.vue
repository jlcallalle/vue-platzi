<template>
  <div class="hello">
    <!-- <p>Componente: VueExpresions.vue</p> -->
    <h2>Expresiones</h2>
    <p> {{ welcome }}</p>
    <p>{{ 1 + 1 }}</p>
    <p>{{ 'Hola' + ' Mundo'}}</p>
    <p>{{ true ? true : false }}</p>
    <p>{{ person.name }}</p>
    <p>{{ person.name.toUpperCase() }}</p>
    <p>{{ JSON.stringify(person)}}</p> 

    <h2>Directivas</h2>
    <h4>v-if - v-show</h4>
    <p v-if="showValue"> {{ value }}</p>
    <p v-else> {{ 'algo más' }}</p>
    <p v-show="showValue"> {{ value }}</p>
    <h4>v-for</h4>

    <h2>Data Binding</h2>
    <h4>v-model</h4>
    <input v-model="valorInput" type="text">
    <p>{{ valorInput }}</p>

    <h4>v-bind:href, v-bind:title</h4>
    <!-- <a :href="url">link</a> -->
    <a v-bind:href="url">link</a>
    <p v-bind:title="messageTitle">
      Mueva el mouse sobre mí durante unos segundos
      para ver mi título enlazado dinámicamente.
    </p>

    <h2>Computer Properties</h2>
    <input v-model="name" type="text"> - 
    <input v-model="lastname" type="text">
    <p>{{ fullname }}</p>

    <h2>Watchers</h2>
    <p>ejemplo consola</p>

  </div>
</template>

<script>
export default {
  name: 'VueExpresions',
  data () {
    return {
      name: '',
      lastname: '',
      welcome: 'Hola Vue.js',
      person: {
          name: 'jorge'
      },
      showValue: false,
      value : 'algo',
      todos: [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' }
      ],
      valorInput : '',
      url: 'https://www.google.com/',
      messageTitle: 'Usted cargó esta página el ' + new Date().toLocaleString(),
    }
  },
  computed: {
      fullname () {
          return `${this.name}  ${this.lastname}`
      }
  },
  watch: {
      name (newVal, oldVal) {
          console.log(newVal, oldVal);
      }
  },
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
