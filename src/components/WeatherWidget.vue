<template>
  <div class="weather-widget">
    <h2>Widget Cuaca</h2>
    <div class="search-bar">
      <input v-model="city" placeholder="Masukkan nama kota" @keyup.enter="getWeather" />
      <button @click="getWeather">Cari</button>
    </div>
    <div v-if="weather" class="weather-info">
      <p><strong>Lokasi:</strong> {{ weather.name }}</p>
      <p><strong>Suhu:</strong> {{ weather.main.temp }}°C</p>
      <p><strong>Cuaca:</strong> {{ weather.weather[0].description }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const city = ref('')
const weather = ref(null)

const getWeather = async () => {
  const apiKey = '23f0987b01236b80c30ceeb06f7c8c22'
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`

  try {
    const response = await axios.get(url)
    weather.value = response.data
  } catch (error) {
    console.error(error)
    weather.value = null
  }
}
</script>

<style scoped>
.weather-widget {
  padding: 20px;
  border: 1px solid brown;
  border-radius: 10px;
  max-width: 600px;
  margin: 20px auto;
  text-align: center;
  background-color: #f5f1ea;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  margin-top: 30px;
}

.weather-widget h2 {
  color: #64403e;
  font-size: 36px;
  font-weight: bold;
  margin-bottom: -1px;
}

.search-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.search-bar input {
  flex: 1;
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #faf5ed;
}

.search-bar button {
  padding: 10px 20px;
  border: 1px solid #c2b8aa;
  background-color: #8c6654;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}

.search-bar button:hover {
  background-color: #64403e;
}

.weather-info {
  margin-top: 20px;
}

.weather-info p {
  margin: 5px 0;
  color: #64403e;
}
</style>
