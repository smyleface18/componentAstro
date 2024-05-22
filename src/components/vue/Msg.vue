<script setup>
import {  ref} from "vue";
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
        <p v-if="value">Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis magnam tempore unde adipisci aut vel quod rem, fugiat culpa? Pariatur inventore non magnam in! Voluptas quaerat tempore sunt eum omnis!
        Alias voluptatibus accusamus in, delectus, tempora distinctio atque quisquam repudiandae ut expedita accusantium necessitatibus fugiat molestias porro a quaerat et dolores vero molestiae, aliquam error! Exercitationem dolores minus porro beatae.
        Quasi harum error explicabo ab doloribus consequatur veniam architecto placeat! Nobis atque rerum blanditiis, voluptatibus ad tempore exercitationem fugiat doloribus magnam incidunt, molestiae aut possimus sunt sit placeat tenetur sed.
        Dolor et, nulla ducimus corrupti explicabo repellendus ullam non, laudantium consequatur laboriosam nisi. Officiis commodi nulla tempore vel deserunt temporibus corporis quia ab, architecto provident a adipisci maiores perspiciatis quod.
        Facilis, facere nostrum, consequuntur, mollitia officiis saepe porro harum ut magnam magni asperiores. Iusto quaerat in ex sapiente, quam recusandae quidem, aspernatur explicabo, libero odio eligendi soluta nobis animi sint?
        Voluptatum excepturi repellendus sapiente impedit odio quis eos autem animi, quidem ut consequuntur maxime nam optio ipsa nesciunt sint, repellat ratione veniam. Magni velit quod excepturi autem aut similique nam?
        Magnam sit explicabo voluptatibus? Quas non magnam blanditiis odio animi! Magnam, repellendus repellat illum perspiciatis assumenda tempore doloribus labore quo at praesentium, corrupti voluptatibus quasi totam in dolor voluptas quod.
        Numquam libero unde, aspernatur aperiam atque nisi dolores voluptate eius. Ullam, natus? Dolore blanditiis velit ab fuga minima dolorem natus, sapiente cum nostrum. Atque debitis blanditiis eius repellendus laborum itaque.
        Quas modi placeat delectus sit numquam ab quia rerum deleniti distinctio cumque adipisci aperiam, laudantium illum quo quibusdam non, libero beatae at necessitatibus quaerat? Officia expedita tempore debitis facilis earum!
        Omnis magnam quam, deserunt dolorum doloribus vero perferendis non autem officia, obcaecati natus voluptatem eum. Accusantium est voluptatum quas. Maiores voluptate officiis molestias similique sequi nostrum illum repudiandae enim quam.</p>
    </div>
</template>