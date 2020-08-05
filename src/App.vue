<template>
  <Main/>
  <!-- <Weather :weather='weather'/> -->
</template>

<script>
import Main from './components/Main';
// import Weather from './components/Weather';

export default {
  name: 'App',

  components: {
    Main,
    // Weather
  },

  data: () => ({
    //
    weather: {
      location: 'Davison, MI',
      condition: 'Cloudy',
      precipitation: '10%',
      temperature: '76.4 °F',
      humidity: '68%',
      wind: '12 mph'
    }
  }),
};
</script>

<style>

</style>