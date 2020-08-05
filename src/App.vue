<template>
  <Main/>
</template>

<script>
import Main from './components/Main';

export default {
  name: 'App',

  components: {
    Main,
    // Weather
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');

body {
  color: rgb(214, 210, 210);
  background-color: rgb(163, 158, 158);
  font-family: 'Nunito', sans-serif;
}

</style>