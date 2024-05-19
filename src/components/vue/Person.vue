<script setup>

import {ref} from 'vue';

let person = ref( {  "name": "Caleb",
                "lastName": "Acosta",
                "age": 0})
let change = ref(false);


function ViewChangeName(){
    if( change.value){
        change.value = false;
    }
    else{
        change.value = true;
    }
}
function ChangeName(){

   person.value.name = input_te[0].value;
   input_te[0].value = ""
}
function ChangeAge(){

   person.value.age = input_te[1].value;

}

</script>

<template >
<div class="w-full flex flex-col justify-center items-center">
    <button @click="ViewChangeName()" class="bg-green-700 text-white px-2">Change data</button>
    <div v-show="change"  class="w-full px-1" >
        <input id="input_te"  type="text"   placeholder="Ingresar" class="w-[85%]" >
        <button @click="ChangeName()" class="bg-green-600 w-[15%]">+</button>
        <input id="input_te"  type="text"   placeholder="Ingresar" class="w-[85%]" >
        <button @click="ChangeAge()" class="bg-green-600 w-[15%]">+</button>

    </div>
    <div v-if="person.age >= 18">
        <h4>QUE BUENO QUE ERES MAYOR DE EDAD</h4>
    </div>

    <p>{{ person.name }}  {{ person.age }} </p>
</div>
</template>