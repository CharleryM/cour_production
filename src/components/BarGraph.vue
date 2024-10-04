<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: { Bar },
  data() {
    return {
      chartOptions: {
        responsive: true
      },
      combinedChartData: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
        datasets: [
          {
            label: 'Année précédante',
            data: [40, 20, 12, 24, 55, 35, 15, 77, 85, 45, 43, 14],
            backgroundColor: 'rgba(255, 99, 132, 0.2)',
            borderColor: 'rgba(255, 99, 132, 1)',
            borderWidth: 1
          },
          {
            label: 'Année actuel',
            data: [30, 25, 10, 28, 60, 30, 20, 70, 80, 50, 40, 20],
            backgroundColor: 'rgba(54, 162, 235, 0.2)',
            borderColor: 'rgba(54, 162, 235, 1)',
            borderWidth: 1
          }
        ]
      }
    }
  }
}
</script>

<template>
  <div class="grid-container-3">
      <div class="colomne-grid-graph"></div>
      <div class="canvas">
        <Bar
          id="my-chart-id"
          :options="chartOptions"
          :data="combinedChartData"
        />
      </div>
      <div class="colomne-grid"></div>
    </div>
</template>

<style>
.grid-container-3 {
  display: grid;
  grid-template-columns: auto auto auto;
  padding: 10px;
}

.colomne-grid-graph{
  margin: 50px;
  text-align: center;
}

/* Style du canvas */
.canvas {
display: flex;
  justify-content: center;  
  align-items: center; 
  height: 500px;
}
</style>