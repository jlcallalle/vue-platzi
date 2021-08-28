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
<p>{{ person.name }}</p>
<p>{{ person.name.toUpperCase() }}</p>
<p>{{ JSON.stringify(person)}}</p> 

```
