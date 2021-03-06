# Curso Profesional Vue

## Run Vue CLI
    sudo npm i -g @vue/**cli**
    sudo npm install -g @vue/cli-init
    vue init webpack-simple platzi-music:
        . Project name platzi-music
        . Project description App curso vue.js
        . Author jorge <jlcallalle@gmail.com>
        . License MIT
        . Use sass? Yes.

    cd platzi-music
    npm install
    npm run dev

Nueva Versión:
- $ vue create vue-cli
- $ cd vue-cli
- $ npm run serve


# Manipulación del DOM
## 1.- Expresiones y Propiedades
 Son parametros que ponemos entre llaves y permite representar en pantalla valores de nuestro v-model. 
 Podemos acceder a las propiedades de los objetos y funciones. 

``` html
<h1>{{ msg }}</h1>
<p>{{ 1 + 1 }}</p>
<p>{{ 'Hola' + ' Mundo'}}</p>
<p>{{ true ? 'true' : 'false' }}</p>
<p>{{ person.name }}</p>****
<p>{{ person.name.toUpperCase() }}</p>
<p>{{ JSON.stringify(person)}}</p> 

```
## 2.- Directivas
Marcadores o atributos que agregan a los elementos html para aplicar transformaciones a esos mismos elementos. 
- v-if, v-else
- v-show (display:none)
- v-for

## 3. Data Binding
Data Binding implica que podamos enlazar datos desde nuestra vista a nuestro código y desde nuestro código a nuestra vista.
Esto quiere decir que cada vez que algo se cambie en el código, va a reflejarse automáticamente en la vista, gracias al concepto de reactividad


v-model: permite enlazar input, textarea, select con propiedades de nuestro v-model, permitiendo que el usuario ingrese información y se refresque automaticamente en la vista. (el valor de v-model se debe aregar en data)

``` html
<input v-model="valorInput" type="text">
<p>{{ valorInput }}</p>

 data () {
    return {
      valorInput : '',
    }
  }
```
v-bind(:nombreAtributo): enlaza cualquier atributo de un elemento html, con cualquierda de las propiedades del v-model.

ejemplo: ( v-bind:title="valor", v-bind:href="url")
(el valor de v-bind se debe aregar en data)


``` html
<a v-bind:href="url">link</a>

<p v-bind:title="messageTitle"></p>

 data () {
    return {
      url: 'https://www.google.com/',
      messageTitle: 'Usted cargó esta página el ' + new Date().toLocaleString(),
    }
  }
 ```


 Nota:

El v-model v es un two-way binding (enlace bidireccional), lo que significa que si cambia el valor de entrada

El v-bind es one-way binding (enlace unidireccional), lo que significa que enlaza nuestros datos en un sentido.
También se puede utilizar para vincular atributos HTML.


## 3. Computer Properties
Propiedadades que se calculan a partir de otras propiedades, 
podemos crear propiedades dinamicas, cuando alguna propiedad cambia su valor.
Son funciones que devuelven un valor.
Sirven para generar valores o variables en base a otras propiedades que ya tenemos en el v-model

``` html
<input v-model="name" type="text"> - 
<input v-model="lastname" type="text">
<p>{{ fullname }}</p>

computed: {
    fullname () {
        return `${this.name}  ${this.lastname}`
    }
},
 ```

## 4. Watchers

 Permite ejecutar codigo a partir de que una propiedad de nuestro v-model.
 no devuelven valor, no son propiedades y no pueden ser usadas en expresiones.

 Se enlazan directamente de alguna propiedad de nuestro v-model por lo que se tiene que llamar de la misma manera. es decir si quiero hacer un watch de la variable 'name', el watch deberia llamarse 'name'.

 Ejemplo: Imprime en console valor antes y despues.


``` html
data () {
    return {
      name: '',
  },
  watch: {
      name (newVal, oldVal) {
          console.log(newVal, oldVal);
      }
  },
 ```
 Usos Comunes:

 Se puede usar para llamadas HTTP:
Un uso comun sería desencadenar una llamada HTTP apartir de que un valor input este modificandose (google), cada vez que se presiona una tecla en el input, puedo reforzar la llamada de la búsqueda.

## Manejo de eventos
v-on: directiva que sirve para escuchar eventos del DOM, tales como onclick, onmouseover, mouseout, para ejecutar alguna función.

``` html
<input v-model="nombre" type="text">
<!-- <button v-on:click="format">format</button> --> Se puede usar el @ como shorthand 
<button @click="format">format</button>
<p>{{ formatoNombre }} </p>

methods: {
  format() {
    this.formatoNombre = this.nombre.split(' ').join('-').toUpperCase()
  },
}
 ```

 ## Integracion de Proyecto

 VueIntegra.vue
https://codepen.io/ianaya89/pen/NgEeVO

``` js
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
      tracks: []
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
  }
}
 ```

``` html
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
 ```

 ## Servicios: Consumir APIS

 Interactuar con peticiones HTTP ()
 Se puede integrar con cualquier API pública o privada.

 config.js: almacenamiento

 const configService = {
    apiUrl: 'https://platzi-music-api.herokuapp.com/'
  }
  
export default configService
export permite que el objeto puede ser utilizado.
  

 ## Consumir API's REST 
EndPoint: https://platzi-music-api.herokuapp.com/search?q=muchacha&type=track

Api coincap: 
https://docs.coincap.io/?version=latest
https://api.coincap.io/v2/assets
ttps://api.coincap.io/v2/assets?limit=20