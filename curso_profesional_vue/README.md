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