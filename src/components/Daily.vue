<script setup>
import {ref} from 'vue';



const todoList = [];

let todoListArray = [];

let valueInput = 'New task';

function addToList() {
    todoListArray.push(todoList.value)
    console.log(todoListArray);
}
function addTask(todoListArray) {
    console.log(todoListArray.length);
}
function handlyInput(event){
    this.valueInput = event.target.value;
}
// function addTask() {
//     console.log(1);
// }
</script>
<template>
    <div class="bg-blue-300 p-2 rounded-xl">
        <p> DAily ji est'</p>          
        <div class="bg-blue-100 rounded-xl mx-auto p-2 shadow mb-2">
            <p>Pomodoro tracker</p>
            <div class="shadow-lg p-2 rounded">
                <p>to-do list</p>
                <div class="flex">

                    <input  @input="handlyInput" v-model="todoListArray" class="w-5/6 rounded pl-1" type="text"> 

                    <button @click="addTask" type="submit" class="ml-2">add</button>
                </div>
                <ul>
                    <li class="p-2" v-for="item in todoList"> 
                        <svg width="20" height="20" viewBox="0 0 40 41" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <use xlink:href="../assets/images/operators/operators.svg#pomodoro" />
                        </svg>
                        <span>
                            {{ item }}
                        </span>
                    </li>
                </ul>
            </div>
        </div>
        
        <div class="bg-blue-100 rounded-xl mx-auto p-2 shadow mb-2"></div>
        <div class="bg-blue-100 rounded-xl mx-auto p-2 shadow mb-2"></div>
        <div class="bg-blue-100 rounded-xl mx-auto p-2 shadow mb-2"></div>

    </div>
</template>

