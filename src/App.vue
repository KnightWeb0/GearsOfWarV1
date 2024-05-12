<script setup  lang="ts">
import { ref,computed } from 'vue';
//this is where the input will store its value in this ref 
const gearsName = ref ('');

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
const gearRanksArray = ref(['']);

       // Define your array of items
     //  const items = ref(['item1', 'item2', 'item3']);

    // Convert the array of items to a string
    // const stringItems = computed(() => items.value.join(''));

const convertGearsToStrings = computed(() => gearRanksArray.value.join(''));


//this will push the newly created input into the array 
const addGearToArray = () => {


  //here we are pushing the 
  gearsArray.value.push({
   id: gearsArray.value.length + 1, 
   fullname: gearsName.value ,
   rank:convertGearsToStrings.value,
})

convertGearsToStrings.value = '';

gearsName.value = '';

}

</script>

<template>

<h1>  Gears Registration </h1>
<hr>
<div>

  <h2> Rank:  {{convertGearsToStrings }}</h2>
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
<input type="checkbox" value="Chief Sergeant" v-model="gearkRansArray">
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
<hr>

</div>



  <h2> Gears name:   {{ gearsName }} 
  
<br>
<br>
    <input type="text" v-model="gearsName"> 
    <button @click="addGearToArray">  Add Gear </button>
  
  </h2> 
 

<hr>




<h2> Our Gears </h2>
<div v-for="gear in gearsArray" :key="gear.id"> 
 {{ gear.rank }} {{ gear.fullname }}
</div>





</template>
