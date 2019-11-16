<template>
  <div class="hello">
    <div class="container">
        <h2 id="city">{{city}}</h2>
        <div class="middle">
          <img :src="icon" alt="icon" id="icon">
          <div class="degrees">
            <h1>{{Math.round(temperature)}}</h1>
            <span>°</span>
          </div>
          <h3 id="desc">{{description}}</h3>
        </div>
        
    </div>
  </div>
</template>

<script>
export default {
  name: 'Weather',
  data(){
    return{
    }
  },
  props: [
    'city',
    'description',
    'icon',
    'temperature'
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,h2,h3,span{
  margin: 0;
}

h1{
  font-size: 16rem;
}

h2{
  font-size: 3rem;
}

h3{
  font-size: 1.4rem;
}

span{
  font-size: 6rem;
}
  .container{
    max-width: 550px;
    height: 100vh;
    margin: 0 auto;
    border: 1px solid black;
    display: grid;
    grid-template-rows: 20% 80%;
    text-align: center;
    padding: 25px 5px;
  }
  .degrees{
  display: grid;
  grid-template-columns: auto auto;
  justify-content: center;
}
</style>
