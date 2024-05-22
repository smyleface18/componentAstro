<script setup>
let ArrayWords = ["Hola","Mundo","cruel",":D"];

</script>

<template>

<ul class="w-[100px] h-auto ">
    <li v-for="(word,index) in ArrayWords" :key="index" :class="{'bg-green-600' : (index %2  == 0 )} " class="text-white">{{word}}</li>
</ul>

</template>