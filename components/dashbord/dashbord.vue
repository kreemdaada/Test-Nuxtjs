<template>
  <div>
    <Navbar/>
  </div>  

  <div class="flex flex-col items-center md-60 min-h-screen bg-gray-100">
    <div class="w-full py-4">
      <div class="flex justify-center items-center space-x-4 mb-4">
        <button class="bg-blue-500 hover:bg-blue-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-blue-300">
          Aktien Kaufen
        </button>
        <button class="bg-green-500 hover:bg-green-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-green-300">
          Aktien Preis
        </button>
        <button class="bg-red-500 hover:bg-red-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-red-300">
          Aktien Name
        </button>
      </div>
    </div>
    <div class="w-full px-4">
      <canvas ref="myChartCanvas" class="w-full h-80"></canvas>
    </div>
  </div>

</template>
<script>
import { Chart, registerables } from 'chart.js';
Chart.register(...registerables);

export default {
  mounted() {
    this.createChart();
  },
  methods: {
    createChart() {
      const ctx = this.$refs.myChartCanvas.getContext('2d');
      new Chart(ctx, {
        type: 'bar',
        data: {
          labels: ['Data 1', 'Data 2', 'Data 3'],
          datasets: [{
            label: 'Data',
            data: [10, 20, 30],
            backgroundColor: [
              'rgba(75, 192, 192, 0.2)',
              'rgba(255, 159, 64, 0.2)',
              'rgba(255, 99, 132, 0.2)',
            ],
            borderColor: [
              'rgba(75, 192, 192, 1)',
              'rgba(255, 159, 64, 1)',
              'rgba(255, 99, 132, 1)',
            ],
            borderWidth: 1,
          }],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            y: {
              beginAtZero: true,
            },
          },
        },
      });
    },
  },
};
</script>

<style>
/* Add custom styles for the chart container */
.w-96 {
  width: 800px; /* Adjust width to desired size */
}

.h-80 {
  height: 400px; /* Adjust height to desired size */
}

/* CSS to position the navbar at the top of the page */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #fff; /* Change this to your desired background color for the navbar */
  z-index: 999; /* Make sure the navbar appears above other elements */
}
</style>
