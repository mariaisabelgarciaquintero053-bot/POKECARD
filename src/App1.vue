<script setup>
import { ref } from 'vue'

const url = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoZdB2Xy1t_vUay1PpSbUDHmcSVf-9MS17rdYqB9qiwg&s=10"


const altImage= "Image dragon"
const id = 3
const hasActivo= false

const tipo="error"

const porcentaje= 4

const form = ref({
  name: "Isabel",
  edad: 20,
  email:"isabel.garcia@example.com"
})

</script>


<template>
   <img :src="url" :alt="altImage">
   <a :href="`/estudiantes/${id}`">VER</a>
   <button :disabled="hasActivo">Click</button>
   
   <p :class="{activo: hasActivo, error: !hasActivo}"> </p>
   <p :class="`alerta alerta--${tipo}`"> </p>
   <p :style="{width : porcentaje + '%'}"> </p>
   
<input @keyup.enter="buscar"/>
<form @submit.prevent=""></form>

    <button></button>


   <input v-model="form.name"/>
   <input v-model.number="form.edad"/> 
   <input v-model.trim="form.email"/>

   <select v-model ="form.rol">
    <option value="">Seleccione un rol</option>
    <option >Admin</option>
    <option >User</option>
   </select>


</template>

