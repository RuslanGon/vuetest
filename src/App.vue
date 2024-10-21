<template>
  <div class="wrapper">
    <h1>Приложение погоды</h1>
    <p>Узнайте погоду в {{ city === '' ? 'вашем городе' : cityName }}</p>
    <input type="text" @input="city = $event.target.value" placeholder="введите ваш город">
    <button v-if="city !== ''" @click="getWeather()">узнать погоду</button>
    <button disabled v-else>введите ваш город</button>
    <p class="text">{{ error }}</p>
    <p v-if="info && info.main">Температура: {{ info.main.temp }}°C</p>
    <p v-if="info && info.main">Ощущается как: {{ info.main.feels_like }}°C</p>
  </div> 
</template>

<script> 
import axios from 'axios';

export default {
  data() {
    return {
      city: '',
      error: '',
      info: null
    }
  },
  computed: {
    cityName() {
      return "< " + this.city + " >"; 
    }
  },
  methods: {
    getWeather() {
      if (this.city.trim().length < 2) {
        this.error = 'Введите более 1 символа';
        return false;
      }
      this.error = '';
      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=581f2fd2d7c7cd7fdada18bd7ec0b718`)
      .then(res => {
        this.info = res.data;
        this.error = ''; 
      })
      .catch(err => {
        this.error = 'Не удалось получить данные о погоде. Пожалуйста, проверьте правильность ввода города.';
        this.info = null; 
      });
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
