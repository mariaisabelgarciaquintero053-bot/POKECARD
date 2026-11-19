<script setup>
import TarjetaSaludo from './components/TarjetaSaludo.vue'
import {getPokemon} from './api/pokeapi.js'

import {ref, watch, computed, onBeforeMount, onMounted,onBeforeUpdate,onUpdated,onUnmounted} from ''

let loading = ref(true)
let pokemon = ref ({})

onBeforeMount(()=>{
  console.log("Aún no hay DOM")
})

onMounted(async () => {
    pokemon.value = await getPokemon("pikachu")
    console.log(pokemon.value)
    loading.value = false


  })

onBeforeUpdate(() => {
  console.log("Antes de actualizar ")
})

onUpdated(() => {
  console.log("Despues de actualizar") 
})
onUnmounted(() => {
  console.log("Se ha destruido el componente")
})

watch(hora,(newHora, oldHora) => {
  console.log(`La hora ha cambiado de ${oldHora} a ${newHora}`)
})



</script>


<template>
  <p v-if="loading">Cargando...</p>
  <div v-else>
    <h1>{{ pokemon.name }}</h1>
    <img :src="pokemon.sprites.front_default" :alt="pokemon?.name" width="200" height="200" />
  </div>
  <p class="hora">Hora actual: {{ hora }}</p>
</template>