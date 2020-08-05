<template>
  <div class="card grow" :class="weatherConditionImage(this.weather.condition)">
    <div class="card-title">CURRENT WEATHER</div>
    <div class="location">
      <div class="icon"><weather-icon icon="wind-direction"/></div>
      {{ weather.location}}
    </div>
    <div class="weather-overview">
      <div class="overview-wrapper">
        
        <div class="temperature">
          <weather-icon class="icon-size condition-icon" :icon="weatherConditionIcon(this.weather.condition)"/>
          {{ weather.temperature }}
          </div>
      </div>
    </div>
    <div class="weather-details">
      <div class="details-wrapper">
        <div class="label">
          <div class="icon"><weather-icon icon="rain"/></div>
            Precipitation
          </div>
        <div class="metric">{{ weather.precipitation}}</div>
      </div>
      <div class="details-wrapper">
        <div class="label">
          <div class="icon"><weather-icon icon="humidity"/></div>
            Humidity
          </div>
        <div class="metric">{{ weather.humidity}}</div>
      </div>
      <div class="details-wrapper">
        <div class="label">
          <div class="icon"><weather-icon icon="strong-wind"/></div>
            Wind
          </div>
        <div class="metric">{{ weather.wind}}</div>
      </div>
    </div>
  </div>
</template>

<script>
import WeatherIcon from 'vue-weathericons';
//have to change scss to css in node-modules for vue-weathericons
//pull request submitted, temp workaround

export default {
  name: 'Weather',
  props: {
    weather: Object
  },
  components: {
    WeatherIcon
  },

  data: () => ({
  }),
  methods: {
    weatherConditionIcon(condition) {
      if(condition === 'Sunny'){
        return 'day-sunny';
      }
      if(condition === 'Cloudy'){
        return 'day-cloudy';
      }
      if(condition === 'Windy'){
        return 'day-windy';
      }
      if(condition === 'Rainy'){
        return 'day-rain';
      }
      else {
        return 'na'
      }
    },
    weatherConditionImage(condition) {
      if(condition === 'Sunny'){
        return 'bg-image-sunny';
      }
      if(condition === 'Cloudy'){
        return 'bg-image-cloudy';
      }
      if(condition === 'Windy'){
        return 'bg-image-windy';
      }
      if(condition === 'Rainy'){
        return 'bg-image-rainy';
      }
      else {
        return 'na'
      }
    }
  }
};
</script>

<style scoped>

.bg-image-sunny {
    color: rgb(13, 55, 119);
    background-image: url('./assets/sunny.jpg');
    background-size: cover;
}

.bg-image-cloudy {
    color: white;
    background-image: url('./assets/cloudy.jpg');
    background-size: cover;
}

.bg-image-windy {
    color: rgb(58, 56, 56);
    background-image: url('./assets/windy.jpg');
    background-size: cover;
}

.bg-image-rainy {
    background-image: url('./assets/rainy.jpg');
    background-size: cover;
}

.card-title {
  font-size: 1.7rem;
  font-weight: 900;
}

.card {
  height: 100%;
  width: 100%;
  padding: 1em;
  cursor: pointer;
}

.grow { 
  transition: all .2s ease-in-out;
}

.grow:hover, .grow:active {
  transform: scale(1.05);
}

.location {
  font-weight: bold;
}

.weather-overview {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
}

.weather-details {
  display: flex;
  flex-direction: column;
}

.overview-wrapper {
  display: flex;           display: -webkit-flex;
  flex-direction: column;     -webkit-flex-direction: row;
  flex-grow: 0;            -webkit-flex-grow: 0;
  justify-content: center;
  padding: 1rem;
}

.details-wrapper {
  display: flex;           display: -webkit-flex;
  flex-direction: row;     -webkit-flex-direction: row;
  flex-grow: 0;            -webkit-flex-grow: 0;
  justify-content: space-between;
  font-size: 1.35em;
}

.label {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.icon {
  display: inline-block;
  padding-right: 10px;
  height: 20px;
  width:20px; 
}

/* .icon-size {
  transform: scale(3) translate(66%, 66%);
} */

/* .condition-icon {
  height: 100px;
  width: 100px;
} */

.temperature {
  font-weight: 900;
  font-size: 3rem;
  white-space: nowrap;
}

.metric {
  font-weight: 800;
}

</style>