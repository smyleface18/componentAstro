<script setup>

let arrayList = ["Hola","Mundo","Cruel"];

</script>



<template>

 <div>
    <p v-for="word in arrayList">{{ word }}</p>
 </div>

</template>