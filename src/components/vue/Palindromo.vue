<script setup>

function palindromo() {
    let wordRevers = "";
    console.log(input_text)
    for (let index = input_text.value.length-1; index >= 0  ; index--) {
        wordRevers += input_text.value.charAt(index);
        
    }

    if (wordRevers == input_text.value) {
        alert("la palabra "+input_text.value+" es una palindromo")
    }
    else {
        alert("la palabra "+input_text.value+" no es una palindromo")
    }
    input_text.value = "";
}
</script>

<template>

    <div class="w-52 h-auto bg-slate-500 flex flex-col">
        <input id="input_text" type="text" placeholder="        Ingresa una palabra">
        <button @click="palindromo()">PALIDROMO?</button>
        
    </div>
</template>