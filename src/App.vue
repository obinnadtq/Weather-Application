<template>
  <div id="app">
    <Weather :city="weather.city_name" :description="weather.weather.description"  :temperature = "weather.temp"/>
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
       weather: [],
       city: 'Lagos,NG'
    }
  },
  methods:{
    updateCity(){
      return this.city
    }
  },
  mounted(){
    const API_KEY = "c564a6cce5c549dcbe096a696326d95d";
    fetch(`https://api.weatherbit.io/v2.0/current?city=${this.city}&key=${API_KEY}`,{
      method: 'get'
    })
    .then((response)=>{
     return response.json()
    })
    .then((jsonData)=>{
      this.weather = jsonData.data[0]
    })
  }
}
</script>

<style>
</style>
