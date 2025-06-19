<template>
  <div class="wrapper">
    <div class="container">
      <h1>Weather App</h1>
      <p>You can know about weather in{{ city === '' ? ' your city' : ' ' + city }} right now!</p>
      <input type="text" v-model="city" placeholder="Type city..." />
      <button v-if="city !== ''" @click="getWeather">Get</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      city: '',
      apiKey: 'b78540f2a8b7db656bc7e40a94cb41d7',
    };
  },
  methods: {
    getWeather() {
      if (this.city.trim() === '') return;

      const url = `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.apiKey}&units=metric&lang=en`;

      axios
        .get(url)
        .then((response) => {
          console.log(response.data);
          alert(`Weather in ${this.city}: ${response.data.weather[0].description}, Temp: ${response.data.main.temp}°C`);
        })
        .catch((error) => {
          console.error('Error fetching weather data:', error);
          alert('Could not fetch weather data. Please check the city name and try again.');
        });
    }
  }
};
</script>

<style scoped>
.wrapper {
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: bisque;
  padding: 20px;
}

.wrapper h1 {
  color: darkblue;
  margin-top: 50px;
}

.wrapper input {
  margin-top: 30px;
  background: transparent;
  border: 0;
  border-bottom: 2px solid darkblue;
  padding: 10px;
}

.wrapper input:focus {
  outline: none;
  border-bottom: 2px solid darkred;
}

.wrapper button {
  margin-top: 30px;
  background-color: darkblue;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  margin: 20px;
}
</style>
