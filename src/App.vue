<script setup>
import { ref } from 'vue'

// const min = 1;
// const max = 7;

let worp = ref({
    1: 0,
    2: 0,
    3: 0,
    4: 0,
    5: 0,
    6: 0,
});


// let randomNumb = (min, max) =>  {
//     return Math.floor(Math.random() * (max - min) + min);
// };


// let randomArr = (min, max) => { 
//     return [...Array(6)].map(() => randomNumb(min, max));
// };


// const cast = ref({
//    1: {id:1, label: randomArr(min, max)}
// })

const diceArray = ref([])

let gooi = () => {
    for (let index = 0; index < 6; index++) {
        diceArray.value.push(Math.ceil(Math.random()*6))        
    }
    
    for (const die in worp.value) {
        worp.value[die] = diceArray.value.filter(number => number == die).length
    };
    
};





</script>

<template>
  <div id="app">
    <button id="btn" @click="gooi">Gooi</button>
  </div>
</template>


<style>
.getal {
    color: red;
}
</style>
