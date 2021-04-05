<template>
  <main class="main">
    
    <Navbar />

    <div class="dashboard">
      <LinearChart />

      <PieChart />

      <BarChart />

      <div class="calendar-container">
        <v-date-picker v-model="picker"  
                       full-width locale="pt-br" 
                       color="#312F2F" 
                       class="calendar">
        </v-date-picker>
      </div>
    </div>

  </main>
</template>

<script>
import Navbar from '../components/Navbar'
import LinearChart from '../components/charts/LineChart'
import PieChart from '../components/charts/PieChart'
import BarChart from '../components/charts/BarChart'

export default {
  name: 'Home',

  components: {
    Navbar,
    LinearChart,
    PieChart,
    BarChart
  },

  data: () => ({
    picker: new Date().toISOString().substr(0, 10)
  })
}
</script>

<style scoped>
  .main {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    min-height: 88vh;
    padding: 0 7%;
  }
  .dashboard {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
    width: 90%;
    min-height: 70vh;
    margin-bottom: 2rem;
    padding: 1rem 0;
  }
  .calendar-container {
    width: 90%;
  }
  .calendar {
    margin: 1rem 0;
    box-shadow: 
      0px 2px 4px -1px rgba(24, 39, 75, 0.12), 
      0px 4px 12px -2px rgba(24, 39, 75, 0.1);
  }
  .masterclass-banner{
    width: 23.3rem;
    margin: 1rem 1.5rem;
    height: auto;
    border-radius: 0.2rem;
  }
  .masterclass-img {
    width: 100%;
  }
</style>
