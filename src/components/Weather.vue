<script setup>
import { onMounted, ref } from 'vue';

const props = defineProps({
    weatherInfo: {
        type: Object,
        require: true
    },
    getWeather: {
        type: function(){},
        require: true
    },
    city: {
        type: String
    },
    date: {
        type: Date
    }
})
let loading = false;
let city = ref('Moscow')
let date = new Date();
const emits = defineEmits(['getWeather'])

function callMethodInParentComponent() {
    emits("getWeather");
}     

</script>

<template>
    <div class="bg-blue-300 rounded-xl mx-auto p-2 shadow mb-2">
         <!-- {{ weatherInfo?.data }}  -->
        <div class="bg-blue-400 flex p-2 rounded-3xl">
            <img class="w-4" src="/src/assets/images/search.svg" >                
            <input  @keyup.enter="callMethodInParentComponent" :v-model="city" class="ml-1 rounded-3xl pl-2 w-11/12" type="text" placeholder="City">
        </div>
        <div class="flex py-6 px-2 justify-between">
            <p>Weather in <span> {{ weatherInfo?.data.name }} </span> </p>
            <span class=""> updated at {{ date?.toLocaleTimeString() }} </span>
            <img class="w-4" @click="callMethodInParentComponent" :src="loading ? `/src/assets/images/loading.svg` : `/src/assets/images/refresh.svg`" alt="">
        </div>
        <div class="grid grid-cols-3 gap-2">
            <div class="col-span-2 bg-slate-200 rounded p-2 flex justify-around">
                <span>Today</span> 
                <span> {{ date.toLocaleDateString() }}</span>
            </div>
            <div class="p-2 bg-slate-200 rounded text-center"> {{ Math.round(weatherInfo?.data?.main?.temp) }} C</div>
            <div class=" grid justify-center">
                <img :src="`/src/assets/weather-main/${weatherInfo?.data?.weather[0].description}.png`" alt="">
            </div>
            <div class="p-2 bg-slate-200 rounded text-center"> {{ weatherInfo?.data?.weather[0].description}} </div>
            <div class="p-2 bg-slate-200 rounded text-center"> {{ weatherInfo?.data?.wind?.speed }} m/s </div>
        </div>
    </div>
</template>
