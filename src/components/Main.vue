<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-cog</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Settings</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Dashboard</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <div 
        class="cards">
        <Weather class="card" :weather='weather'/>
        <div class="card"></div>
        <div class="card"></div>
        <div class="card"></div>
        <div class="card"></div>
        <div class="card"></div>
      </div>
    </v-main>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import Weather from './Weather'

  export default {
    props: {
      source: String,
    },
    components: {
      Weather
    },

    data: () => ({
      drawer: null,
      weather: {
        location: 'Davison, MI',
        condition: 'Cloudy',
        precipitation: '10%',
        temperature: '76.4 °F',
        humidity: '68%',
        wind: '12 mph'
      }
    }),

    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>

<style scoped>

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(265px, 1fr));
  grid-auto-rows: 300px;
  grid-gap: 20px;
  margin: 20px;
}

.card {
  align-items: center;
  justify-content: space-between;
  padding: 20px;
  background-color: #333947;
}
</style>