<script setup>
import { ref } from 'vue'

const min = 1;
const max = 7;

let worp = {
    1: 0,
    2: 0,
    3: 0,
    4: 0,
    5: 0,
    6: 0,
};


let randomNumb = (min, max) =>  {
    return Math.floor(Math.random() * (max - min) + min);
};


let randomArr = (min, max) => { 
    return [...Array(6)].map(() => randomNumb(min, max));
};


const cast = ref({
   1: {id:1, label: randomNumb(min, max)},
   2: {id:2, label: randomNumb(min, max)},
   3: {id:3, label: randomNumb(min, max)},
   4: {id:4, label: randomNumb(min, max)},
   5: {id:5, label: randomNumb(min, max)},
   6: {id:6, label: randomNumb(min, max)},
})


let gooi = () => {
    document.getElementById("btn").onclick = gooi;
    console.log('Er is gegooid');
    let diceArray = randomArr(min, max);
    
    for (const die in worp) {
        let numberDie = diceArray.filter(number => number == die).length
        worp[die] = numberDie
        getal[die-1].innerHTML = numberDie
    };
};





</script>

<template>
  <div id="app">
    <button id="btn" @click="gooi">Gooi</button>

    <ul v-for="({id, label}, index) in cast" :key="id">
    {{ id }}
    {{ label }}
    </ul>
    

 
  </div>
</template>


<style>
.getal {
    color: red;
}
</style>
