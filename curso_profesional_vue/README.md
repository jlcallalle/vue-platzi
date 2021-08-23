# Aprender Vue

## Expresiones
Una expresión representa el valor de las propiedades de data, se puede usar código js, sumar números, expresiones boolenas, funciones.
Son parametros que ponemos entre {}, permite representar en valor de nuestro v-model, 
El sistema de componentes y rendering declarativo es el coreo de Vue.


## Directivas
Son atributos que podemos agregar al html, para aplica transformaciones a esos mismo elementos
ejm: v-show

    sudo npm i -g @vue/cli
    sudo npm install -g @vue/cli-init
    vue init webpack-simple platzi-music, me pregunta

- Project name platzi-music
- Project description App curso vue.js
- Author jorge <jlcallalle@gmail.com>
- License MIT
- Use sass? Yes
    
      cd platzi-music
      npm install
      npm run dev

# Aprender Vue

## Expresiones y Propiedades
Una expresión representa el valor de las propiedades de data, se puede usar código js, sumar números, expresiones boolenas, funciones.

``` html
<h1>{{ msg }}</h1>
<p>{{ 1 + 1 }}</p>
<p>{{ 'Hola' + ' Mundo'}}</p>
<p>{{ true ? 'true' : 'false' }}</p>
<p>{{ person.name }}</p>
<p>{{ person.name.toUpperCase() }}</p>
<p>{{ JSON.stringify(person)}}</p> 

```
JSON.stringify: parciar valor entero de un objeto a string


## Eventos
v-on:click = @click

