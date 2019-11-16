<template>
  <div id="app">
    <Weather :city="weather.name" :description="weather.weather[0].description" :icon = "weather.weather[0].icon" :temperature = "weather.main.temp"/>
  </div>
</template>

<script>
import Weather from './components/Weather.vue'

export default {
  name: 'app',
  components: {
    Weather
  },
  data(){
    return{
       weather: []
    }
  },
  mounted(){
    fetch('https://fcc-weather-api.glitch.me/api/current?lat=35&lon=139',{
      method: 'get'
    })
    .then((Response)=>{
     return Response.json()
    })
    .then((jsonData)=>{
      this.weather = jsonData
    })
  }
}
</script>

<style>
</style>
