<template>
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />

  </template>
  
  <script>
  import { Bar } from 'vue-chartjs'
  import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
  
  ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)
  
  export default {
    name: 'Graph',
    components: { Bar },
    data() {
      return {
        chartData: {
          labels: [ 'January', 'February', 'March' ],
          datasets: [ { data: [40, 20, 12] } ]
        },
        chartOptions: {
          responsive: true
        }
      }
    },
  }
  </script>
  
  <style scoped>
  /* Style du bouton (facultatif) */
  button {
    padding: 10px;
    background-color: #3498db;
    color: white;
    border: none;
    cursor: pointer;
  }
</style>  