<script setup>
import {ref} from 'vue';
let listNumber = [1,2,3,4,5,6,7,8,9,10];
let numbersExit =ref([]);

function par(listNumber){
    numbersExit.value =[]
    listNumber.forEach(element => {
        if( element % 2 == 0 ){
            numbersExit.value.push(element);
        }
        
    });
}
function impar(listNumber){

    numbersExit.value =[]
    listNumber.forEach(element => {
    if( element % 2 != 0 ){
        numbersExit.value.push(element);
    }
    
});
}
</script>

<template >

    <div class="bg-sky-700 w-96 h-[300px] flex flex-col  mx-auto m-10 items-center">
        <butoon @click="par(listNumber)" class="bg-slate-400 h-10 w-[80%]">PARES</butoon>
        <butoon  @click="impar(listNumber)"  class="bg-slate-400 h-10 w-[80%]">IMPARES</butoon>
        <ul>
            <li v-for="number in numbersExit" >{{ number }}</li>
        </ul>
    </div>

</template>