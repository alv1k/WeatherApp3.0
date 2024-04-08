<script setup>
import axios from 'axios'
import { ref } from 'vue'


let src = ref('')
let listOfMemes = null

        
axios.get(`https://api.imgflip.com/get_memes`)
    .then((data) => {
        listOfMemes = data?.data?.data?.memes,
        src.value = listOfMemes[3].url
    },
);

function refreshMemes(random){
    // let random = Math.round(Math.random() * 50);
    src.value = listOfMemes[random].url
    console.log('refreshed ' + src.value);
    return src.value
}

</script>
<template>
    <div class="bg-blue-300 p-2 rounded-xl mt-2">
       <div class="flex mb-2">

           <div class="bg-yellow-300 w-1/2 h-32 text-center p-2 shadow mr-2">
               <p>sticky note</p>
            </div>
            <div class="bg-yellow-300 w-1/2 h-32 text-center p-2 shadow">
                <p>trash bin</p>
                
            </div>
        </div>
        <div class="bg-yellow-400 rounded p-2 shadow mb-2 text-center justify-center">
            <p>meme of the day</p>
            <img :src="src" @click="refreshMemes(Math.round(Math.random() * 100))" class="mx-auto w-52 self-center" alt="">

        </div>
    </div>
</template>