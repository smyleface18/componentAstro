<script setup>

import {ref} from 'vue';

let arrayList = ref([])
let word =ref("");

function addList() {
    
    arrayList.value.push(input_Text.value) ;
    input_Text.value = "";
    word.value = "";

}
function search(){
    let indexNumber = null;
    
    for (let index = 0; index <arrayList.value.length; index++) {
        const element = arrayList.value[index];
        console.log(index)
        console.log(element.toLowerCase())
        console.log(input_search.value.toLowerCase())
        if(element.toLowerCase() === input_search.value.toLowerCase()){
            indexNumber = index;
            break;
            
        }
    }
    return indexNumber;

}

function delet(){
    let index = search()
    delete arrayList.value[index];
    input_search.value = ""; 

}

function taskComplete() {
    aler("Muy bien has completado la task"+ arrayList[search()])
}

</script>

<template>
    <div class="w-screen flex   justify-center mt-14 min-h-16">
        <div class="bg-slate-400  ">
            <input id="input_Text" v-model="word" type="text" class="border-solid border-orange-200 w-9/12">
            <button @click="addList()" class="text-center text-white w-[25%] bg-slate-600">+</button>
            <div class="w-full">
                <h4 class="w-full text-center">Lista</h4>
                <p class=" w-full">{{word}}</p>
                <p class=" w-full" v-for="word in arrayList">{{word}}</p>
            </div>
        </div>
        <div class="bg-slate-400">
            <h4>Buscar tarea</h4>
            <div class="flex w-full">
                <input id="input_search" type="text"  class="w-9/12">
            </div>
            <div class="w-full bg">
                <button @click="delet()" class="w-6/12">❌</button>
                <button class="w-6/12 text-center">✅</button>
            </div>
        </div>
    </div>

</template>