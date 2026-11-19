<script setup>
import { ref } from 'vue'


const message = "Soy Isabel"



</script>


<template>

<article class="tarjeta">   
<h1>Hola</h1>
  <h2> {{ message }} </h2>
  </article> 
</template>


<style long="css">
.tarjeta{
  background: rgb(10, 10, 10);
  border-left: 4px solid rgb(0, 213,255);
  padding: 1rem;
  margin-bottom: 1rem;
}

</style>



