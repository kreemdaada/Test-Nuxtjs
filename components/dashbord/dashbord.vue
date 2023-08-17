<template>
  <div>
  <Navbar/> 
</div>  
  <div>
    <div class="space-between md-60 flex-row ">
      <div class="py-4">
        <div class="flex justify-center items-center space-x-4 mb-4">
          <button
            class="bg-blue-500 hover:bg-blue-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-blue-300"
          >
            Aktien Kaufen
          </button>
          <button
            class="bg-blue-500 hover:bg-blue-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-blue-300"
          >
            Aktien Preis
          </button>
          <button
            class="bg-blue-500 hover:bg-blue-600 text-white font-serif px-6 py-3 rounded-lg focus:outline-none focus:ring focus:border-blue-300"
          >
            Aktien Name
          </button>
        </div>
      </div> 
      <div class="px-4">
        <canvas ref="myChartCanvas" class="h-80"></canvas>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { Chart, registerables } from 'chart.js';


Chart.register(...registerables);

const myChartCanvas = ref<HTMLCanvasElement | null>(null);

onMounted(() => {
  createChart(myChartCanvas.value);
});

function createChart(canvas: HTMLCanvasElement | null) {
  if (!canvas) return;

  const ctx = canvas.getContext('2d');
  if (!ctx) return;

  new Chart(ctx, {
    type: 'bar',
    data: {
      labels: ['Data 1', 'Data 2', 'Data 3'],
      datasets: [
        {
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
        },
      ],
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
}
</script>

<style scoped>


.h-80 {
  height: 400px; /* Passen Sie die Höhe nach Bedarf an */
}

/* CSS, um die Navbar oben auf der Seite zu positionieren */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #fff; 
  z-index: 999; 
}
</style>
