<template>
  <div class="card">
    <div class="card-title">CURRENT WEATHER</div>
    <div class="location">
      <div class="icon"><weather-icon icon="wind-direction"/></div>
      {{ weather.location}}
    </div>
    <div class="weather-overview">
      <div class="overview-wrapper">
        <div class="condition-icon">
          <weather-icon class="icon-size" :icon="weatherConditionIcon(this.weather.condition)"/>
        </div>
        <div class="temperature">
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
      else {
        return 'na'
      }
    }
  }
};
</script>

<style scoped>

.card-title {
  font-size: 1.5rem;
  font-weight: bold;
}

.card {
  height: 100%;
  width: 100%;
  padding: 1em;
}

.location {
  font-weight: bold;
}

.weather-overview {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}

.weather-details {
  display: flex;
  flex-direction: column;
}

.overview-wrapper {
  display: flex;           display: -webkit-flex;
  flex-direction: row;     -webkit-flex-direction: row;
  flex-grow: 0;            -webkit-flex-grow: 0;
  justify-content: center;
}

.details-wrapper {
  display: flex;           display: -webkit-flex;
  flex-direction: row;     -webkit-flex-direction: row;
  flex-grow: 0;            -webkit-flex-grow: 0;
  justify-content: space-between;
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

.icon-size {
  transform: scale(3) translate(66%, 66%);
}

.condition-icon {
  height: 100px;
  width: 100px;
}

.temperature {
  font-size: 3rem;
  white-space: nowrap;
}

.metric {
  font-weight: 800;
}

</style>