<script setup>
import {ref} from 'vue';

let todoList = ref('');
let todoListArray = new ref([]);

function addToList() {
    todoListArray.value.push(todoList.value)
    todoList.value = ''
}
function deleteTodoItem(item) {
    todoListArray.value.splice(todoListArray.value.indexOf(item), 1)
    
}
</script>
<template>
    <div class="bg-blue-300 p-2 rounded-xl">
        <p> Daily </p>          
        <div class="bg-blue-100 rounded-xl mx-auto p-2 shadow mb-2">
            <p>tracker</p>
            <div class="shadow-lg p-2 rounded">
                <p>to-do list</p>
                <div class="flex">

                    <input v-model="todoList" @keyup.enter="addToList()" class="w-5/6 rounded pl-1" type="text" value=""> 

                    <button type="submit" class="ml-2">add</button>

                </div>


                <ul class="w-48 py-1">
                    <li class="border-solid border-black border-[1px] rounded p-1 flex justify-between" v-for="item in todoListArray"> 
                        <img src="../assets/images/icones/streamline-emojis-2.svg" alt="">
                        <span>
                            {{ item }}
                        </span>
                        <img class="" src="../assets/images/icones/streamline-emojis-cloud-2.svg" alt="">
                        <button @click="deleteTodoItem(item)">del</button>
                    </li>
                </ul>
            </div>
        </div>
        <div class="flex justify-between">

            <div class="bg-blue-100 w-1/3 h-40 mr-1 rounded-xl p-2 shadow mb-2">
                <p>doing</p>
            </div>
            <div class="bg-blue-100 w-1/3 rounded-xl p-2 shadow mb-2">
                <p>urgent</p>
                
            </div>
            <div class="bg-blue-100 w-1/3 ml-1 rounded-xl p-2 shadow mb-2">
                <p>done</p>
            </div>
        </div>

    </div>
</template>

