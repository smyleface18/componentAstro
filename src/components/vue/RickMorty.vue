<script setup>
    import {ref} from 'vue';
import Index from '../../pages/index.astro';


const DATAJSON = await fetch('https://rickandmortyapi.com/api/character')
                .then(response => response.json())
                .then(data => data);

                
    let characters = DATAJSON.results;

    characters.forEach(character => {
        character.select = ref(false);
    });
    console.log(characters[0].select.value);
    function select(Index){
        console.log(characters[Index].select.value)
        characters[Index].select.value = !characters[Index].select.value;
    }
</script>
<template>


    <div class="p-2 mt-10 flex items-center w-3/4 hover:shadow-2xl hover:shadow-slate-50 rounded-3xl" v-for="(character,Index) in characters" :key="Index" :class="{'hover:bg-white': character.species == 'Human' & !character.select.value, 'hover:text-black': character.species == 'Human'},{'bg-yellow-300': character.select.value},{'hover:shadow-red-700': character.status == 'Dead'},{'text-black': character.select.value}" >
        <img :src="character.image" alt="" class="rounded-full w-2/6">
        <div class="w-full px-4"> 
            <h6 class="font-semibold text-3xl w-full text-center">{{character.name}}</h6>
            <p>{{character.status}}
                <svg v-if="character.status == 'Dead'" class="size-12" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 512 512"><path fill="currentColor" d="M256 16C123.452 16 16 123.452 16 256s107.452 240 240 240s240-107.452 240-240S388.548 16 256 16m147.078 387.078a207.253 207.253 0 1 1 44.589-66.125a207.332 207.332 0 0 1-44.589 66.125"/><path fill="currentColor" d="M168 320h176v32H168zm42.63-91.958l-24.042-21.371l21.37-24.041l-23.916-21.26l-21.371 24.042l-24.041-21.37l-21.26 23.916l24.042 21.371l-21.37 24.041l23.916 21.26l21.371-24.042l24.041 21.37zm173.328-45.412l-23.916-21.26l-21.371 24.042l-24.041-21.37l-21.26 23.916l24.042 21.371l-21.37 24.041l23.916 21.26l21.371-24.042l24.041 21.37l21.26-23.916l-24.042-21.371z"/></svg>
                <svg v-else-if="character.status == 'Alive'" class="size-12"  xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 15 15"><path fill="currentColor" fill-rule="evenodd" d="M7.5.877a6.623 6.623 0 1 0 0 13.246A6.623 6.623 0 0 0 7.5.877M1.827 7.5a5.673 5.673 0 1 1 11.346 0a5.673 5.673 0 0 1-11.346 0m3.21 1.714a.5.5 0 1 0-.82.572A3.996 3.996 0 0 0 7.5 11.5c1.36 0 2.56-.679 3.283-1.714a.5.5 0 0 0-.82-.572A2.996 2.996 0 0 1 7.5 10.5a2.996 2.996 0 0 1-2.463-1.286m.338-2.364a.875.875 0 1 0 0-1.75a.875.875 0 0 0 0 1.75m5.125-.875a.875.875 0 1 1-1.75 0a.875.875 0 0 1 1.75 0" clip-rule="evenodd"/></svg>
                <svg v-else class="size-12" xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 256 256"><path fill="currentColor" d="M138 180a10 10 0 1 1-10-10a10 10 0 0 1 10 10M128 74c-21 0-38 15.25-38 34v4a6 6 0 0 0 12 0v-4c0-12.13 11.66-22 26-22s26 9.87 26 22s-11.66 22-26 22a6 6 0 0 0-6 6v8a6 6 0 0 0 12 0v-2.42c18.11-2.58 32-16.66 32-33.58c0-18.75-17-34-38-34m102 54A102 102 0 1 1 128 26a102.12 102.12 0 0 1 102 102m-12 0a90 90 0 1 0-90 90a90.1 90.1 0 0 0 90-90"/></svg>
            </p>
            <p>Especie: {{ character.species }}</p>
            <p>Genero: {{ character.gender }}</p>
            <p>Origin: {{ character.origin.name }}</p>

        </div>
        <button class="bg-white text-black rounded-l-full h-10 px-2 mr-[-8px] hover:bg-black hover:text-white" @click="select(Index)">SELECCIONAR</button>
    </div>
    

</template>