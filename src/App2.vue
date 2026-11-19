<script setup>
import TarjetaSaludo from './components/TarjetaSaludo.vue'

import { ref } from 'vue'

const contador = ref(0)

const frutas = ref(
  ["Manzana", "Pera", "Naranja"])

  const estudiantes =ref([
    {
      id:1,
      nombre: "Isabel",
      edad: 20
    },
      {
      id:2,
      nombre: "Laura",
      edad: 29
    },
    {
      id:3,
      nombre: "Sofia",
      edad: 19
    }
  ])

function incrementar() {
  contador.value++
}
 
const number = 1
const number2 = 2

const valor = ref(0)

function sumar() {
  valor.value = number + number2
}
function restar() {
  valor.value = number - number2
}
function multiplicar() {
  valor.value = number * number2
}
let edad = ref(10)
</script>


<template>

<h1>Mi primera APP</h1>
<tarjetaSaludo />
<tarjetaSaludo />
<tarjetaSaludo />

<p>El numero es:{{ contador }}</p>
<button @click="incrementar">Incrementar</button>
<button @click="contador = 0">Reset</button>

<hr>


<p> El valor de la operacion es {{ valor }}</p>
<button @click="sumar">Sumar</button>
<button @click="restar">Restar</button>
<button @click="multiplicar">Multiplicar</button>
<hr>
<p v-if="edad > 18">  Eres mayor de edad</p>
<p v-else-if="edad === 18">  Tienes 18 años</p>
<p v-else> Eres un adulto </p>

<button @click="edad = 19"> 19 años</button>
<button @click="edad = 10"> 10 años</button>


<br>

<ul>
  <li v-for="fruta in frutas" :key="fruta"> 
    {{ fruta }} 
  </li>

<template>
  <li v-for="estudiante in estudiantes" 
  :key="estudiante.id"> 

  <template v-if="estudiante.edad>=22">
  Hola soy {{ estudiante.nombre }} y tengo
  {{ estudiante.edad }} años</template>
  
  </li>
 </template>
</ul>


<!--contador mejorado-->
<h1 :class="{negativo: contador < 0, positivo:contador > 0}"></h1>

<button @click = "incrementar"> +1 </button>
<button @click="decrementar" :disabled="contador===-5">-1</button>
<button @click="reiniciar">Reiniciar</button>


</template>

<style lang="css">
  .positivo{
    color: rgb(73, 228, 53);
  }
  .negativo{
    color: rgb(228, 73, 73);
  }
</style>