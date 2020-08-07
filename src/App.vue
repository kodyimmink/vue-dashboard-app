<template>
<div class="flex flex-col h-screen">
  <div class="bg-blue-400">
    <header-section/>
  </div>
  <div class="flex flex-1 bg-blue-300 overflow-y-hidden">
    <sidebar/>
    <dashboard/>
  </div>
</div>
</template>

<script>
import HeaderSection from './components/Header/Header';
import Sidebar from './components/Sidebar/Sidebar';
import Dashboard from './components/Dashboard/Dashboard';

export default {
  name: 'App',

  components: {
    HeaderSection,
    Sidebar,
    Dashboard
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');

body {
  color: white;
  background-color: rgb(163, 158, 158);
  font-family: 'Nunito', sans-serif;
}

</style>