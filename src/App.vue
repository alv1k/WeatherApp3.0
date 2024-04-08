<script setup>
import Weather from './components/Weather.vue';
import Daily from './components/Daily.vue';
import HomeStatus from './components/HomeStatus.vue';
import QuestionBlock from './components/QuestionBlock.vue';
import StickyNotes from './components/StickyNotes.vue';
import { onMounted, ref } from 'vue';
import axios from 'axios';
import { weatherAPI_URL, weatherAPI_KEY } from './constants'

let weatherInfo = ref(null);
let city = ref('Yakutsk');

function getWeather() {
  // fetch(`${weatherAPI_URL}?q=${city.value}&appid=${weatherAPI_KEY}&units=metric`)
  //   .then((response) => response.json())
  //     .then((data) => weatherInfo.value = data)

  axios.get(`${weatherAPI_URL}?q=${city.value}&appid=${weatherAPI_KEY}&units=metric`)
    // .then((response) => response.json())
      .then((data) => weatherInfo.value = data)
}
function getTime(){
    this.date = new Date();
    return data;
}

onMounted(getWeather)

// const getAxiosWeather = async () => {
//   try {
//     const response = await axios.get(`${weatherAPI_URL}?q=Yakutsk&appid=${weatherAPI_KEY}&units=metric`)
//     weatherInfo = response.data
//   } catch (err) {
//     console.error(err)
//   }
// }
// onMounted(getAxiosWeather)

</script>
<template>
  <div class="bg-blue-100 p-2">
    <Weather :getWeather="getWeather" :weatherInfo="weatherInfo" />
    <HomeStatus />
    <Daily />
    <QuestionBlock />
    <StickyNotes />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
