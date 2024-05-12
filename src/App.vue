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
//this will store the rank of the gears
const gearRanksArray = ref([]);

//this will push the newly created input into the array 
const addGearToArray = () => {
  

}

</script>

<template>

<h1>  Gears Registration </h1>

<input type="text" v-model="gearsInput">

<div>
  <hr>
  <label>
<input type="checkbox" value="Private" v-model="gearRanksArray">
Private
</label>

<label>
<input type="checkbox" value="Corporal" v-model="gearRanksArray">
Corporal
</label>

<label>
<input type="checkbox" value="Sergeant" v-model="gearRanksArray">
Sergeant
</label>

<br>

<label>
<input type="checkbox" value="Chief Sergeant" v-model="gearRanksArray">
Chief Sergeant
</label>

<label>
<input type="checkbox" value="Lieutenant" v-model="gearRanksArray">
Lieutenant
</label>



<label>
<input type="checkbox" value="First Lieutenant" v-model="gearRanksArray">
First Lieutenant
</label>

<br>

<label>
<input type="checkbox" value="Captain" v-model="gearRanksArray">
Captain
</label>

<label>
<input type="checkbox" value="Major" v-model="gearRanksArray">
Major
</label>

<label>
<input type="checkbox" value="Lieutenant Colonel" v-model="gearRanksArray">
Lieutenant Colonel 
</label>
<br>
<label>
<input type="checkbox" value="Colonel" v-model="gearRanksArray">
Colonel
</label>

<label>
<input type="checkbox" value="General" v-model="gearRanksArray">
General
</label>


</div>

<br>
{{ gearRanksArray  }}
{{ gearsInput }}

<br>
<br>

<div v-for="gear in gearsArray" :key="gear.id"> 
 {{ gear.rank }} {{ gear.fullname }}
</div>





</template>
