<script setup  lang="ts">
import { ref } from 'vue';
//this is where the input will store its value in this ref 
const gearsInput = ref ('');

const gearsArray = ref([
{
  id: 1,
  fullname: 'Marcus Fenix',
  rank: 'Sergeant'
}, 

{
  id: 3,
  fullname: 'Bardry Salaman',
  rank: 'General'
}, 

]);
</script>

<template>

<h1>  Gears Registration </h1>

<input type="text" v-model="gearsInput">
<br>
{{ gearsInput }}

<br>
<br>

<div v-for="gear in gearsArray" :key="gear.id"> 
 {{ gear.rank }} {{ gear.fullname }}
  
</div>

</template>
