<script setup>
import { ref } from 'vue'

let worp = ref({
      1: 0,
      2: 0,
      3: 0,
      4: 0,
      5: 0,
      6: 0,
  });


const numArray = ref([1, 2, 3, 4, 5, 6,])

const diceArray = ref([])

const gooi = () => {
  
  diceArray.value = []

    for (let index = 0; index < 6; index++) {
        diceArray.value.push(Math.ceil(Math.random()*6))        
    }
    
    for (const die in worp.value) {
        worp.value[die] = diceArray.value.filter(number => number == die).length
    }; 
    
    console.log(worp.value)
};


</script>


<template>

  <div id="app">
    <button id="btn" @click="gooi">Gooi</button>
  </div>
  <div class="nummers">
    <li v-for="nummer in numArray">
      {{ nummer }}
    </li>
  </div>
  <div class="aantal">
    <li v-for="worpen in worp">
        {{ worpen }}
    </li>
  </div>
  
</template>


<style>
#btn {
  position: absolute;
  width: 50px;
  height: 20px;
  top: 170px;
  left: 11px;
}
.nummers{
  list-style-type: none;
  position: absolute;
  left: 10px;
  border-bottom: 50px;
}

.nummers li {
  padding: 3px;
}

.aantal {
  list-style-type: none;
  position: absolute;
  left: 50px;
}

.aantal li {
  padding: 3px;
}
</style>
