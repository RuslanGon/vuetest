<template>
  <div class="wrapper">
    <h1>Weather Application</h1>
    <p>Find out the weather in {{ city === '' ? 'your city' : cityName}}</p>
    <input type="text" @input="this.city = $event.target.value" placeholder="enter yuor city">
    <!-- <input type="text" v-model="city" placeholder="enter yuor city"> -->
    <button v-if="city != ''" @click="getWeather()">get weather</button>
    <button disabled v-else>enter your weather</button>
    <p class="text">{{ error }}</p>
  </div> 
</template>

<script> 
export default {
  data() {
    return {
      city: '',
      error: ''
    }
  },
  computed: {
    cityName() {
      return "< " + this.city + " >" 
    }
  } ,
  methods: {
    getWeather() {
      if (this.city.trim().length < 2) {
        this.error = 'enter more than 1 characters'
        return false
      }
      this.error = ''
    }
  }
}

</script>


<style scoped>
.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: rgb(48, 46, 46);
  color: white;
  padding: 20px;
  text-align: center;
}

.wrapper h1 {
  margin-top: 50px;
  padding-bottom: 20px;
}

.wrapper input {
  margin-top: 30px;
  background-color: transparent;
  border: 0;
  border-bottom: 2px solid gold;
  color: white;
  font-size: 14px;
  padding: 5px 8px;
  outline: none;
}

.wrapper input:focus {
  border-bottom-color: white;
}

.wrapper button {
  background-color: black;
  color: white;
  padding: 10px 10px;
  border: none;
  border-radius: 15px;
  cursor: pointer;
  margin-left: 20px;
}

.wrapper button:hover {
  background-color: white;
  color: black;
}

.wrapper button:disabled {
  background-color: gold;
  color: black;
}

.text {
  color: white;
  padding-top: 20px;
}
</style>
