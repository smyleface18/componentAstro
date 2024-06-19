<script setup >

import {  ref} from "vue";

defineProps({
  title: String,
  link : String
  
})

let value = ref(false);


function view(){

    if( value.value == true ){  
             
        value.value  = false
        
    
    }    
    else {
        value.value  = true
    }
}
</script>
<template>

    <div>
        <button @click="view()" class="bg-slate-600 w-full">Click</button>
        <div v-if="value">
            <p class="h-20" >{{ title }}</p>
            <p class="h-20">{{ link }}</p>
            <img src={{link}} alt="">
        </div>


    </div>
</template>