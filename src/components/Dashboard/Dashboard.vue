<template>
    <div class="flex-1 content-area overflow-y-auto bg-blue-600">
        <div class="grid grid-flow-row grid-cols-3 grid-rows-3 gap-5 p-5">
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
            <div class="item">
                <Weather class="weather-card" :weather='weather'/>
            </div>
        </div>
        
    </div>
  
</template>

<script>
import Weather from '../Weather/Weather';

export default {
  name: 'Content',
  components: {
    Weather
  },

  data: () => ({
    //
    weather: {
      location: 'Davison, MI',
      condition: 'Sunny',
      precipitation: '10%',
      temperature: '76 °F',
      humidity: '68%',
      wind: '12 mph'
    }
  }),
};
</script>

<style>

.grid-container {
    padding: 1rem;
    display: grid;
    /* grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); */
    /* This is better for small screens, once min() is better supported */
    /* grid-template-columns: repeat(auto-fill, minmax(min(300px, 100%), 1fr)); */
    /* grid-template-rows: repeat(auto-fill, minmax(min(300px, 100%), 1fr)); */
    /* grid-gap: 1rem; */
    /* This is the standardized property now, but has slightly less support */
    grid-template-columns: repeat(auto-fill, minmax(min(300px, 100%), 1fr));
    gap: 1rem;
    justify-items: stretch;
}

.weather-card {
    box-shadow:10px 10px 20px 5px #1a80e0; 
}

</style>