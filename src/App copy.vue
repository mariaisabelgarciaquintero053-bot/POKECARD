<script setup>
import { ref } from 'vue'


const number = 1
let number2 = ref("Hola Mundo")

console.log(number)
console.log(number2.value)

</script>


<template>
  <h1 class="color-title">Hello  World</h1>
  <h1 class="color-title"> {{ number.toUpperCase() }}</h1>
  <h1 class="color-title"> {{ number2.toLowerCase()}}</h1>
  <h1 class="color-title"> {{ number2.length}}</h1>
  <h1 class="color-title"> {{ number2.includes("h")}}</h1>
  <h1 class="color-title"> {{ }}</h1>
  <h1 class="color-title"> {{ 2 + 5}}</h1>
  <h1 class="color-title"> {{number < 10 ? "Menor que 10" : "Mayor que 10"}}</h1>
</template>



<style lang="css">
  .color-title {
    background: #e0e0e0;
    text-align: center;
    color: blue;
  }
</style>