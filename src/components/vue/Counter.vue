<script setup>
import {ref} from "vue";

let number = ref(0);
let time = ref(0)

let interval

function add(){
    
    if(number.value == 0){
        interval = setInterval(() => {
            time.value++
        },1000)
    }
    number.value++;
    if(number.value == 10){
        clearInterval(interval)
    }

}
</script>


<template>

    <div class="w-screen flex justify-center pt-10 flex-col items-center">
        <button  @click="add" class="bg-yellow-300 w-24 p-5 rounded hover:cursor-crosshair select-none hover:bg-red-400">Count: {{number}} </button>
        <span v-show="number > 0" class="float-right mt-5 font-bold text-xl bg-blue-500 py-2 px-4 rounded ">time: {{time}}</span>
        <h4 v-if="number == 0" class="mt-5 font-semibold bg-yellow-200 px-2 rounded" >CLICKEAR? O MIEDO 🐔</h4>
        <h4 v-if="number > 0" class="mt-5 font-semibold bg-cyan-200 px-2 rounded" >GO! 🐢 </h4>
    </div>
  
</template>