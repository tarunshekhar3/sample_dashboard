<template>
  <div class="bg-white p-6 rounded-lg">
    <div class="flex justify-between items-center mb-6">
      <h3 class="text-lg font-semibold">Income Statistics</h3>
      <div class="flex items-center gap-4">
        <button class="text-sm text-gray-500 hover:text-gray-700 flex items-center">
          Advance Filter
          <ChevronRightIcon class="w-4 h-4 ml-1" />
        </button>
      </div>
    </div>

    <!-- Income Details -->
    <div class="flex items-center gap-4 mb-6">
      <div class="flex items-center gap-2">
        <div class="w-8 h-8 bg-gray-100 rounded-full flex items-center justify-center">
          <CalendarIcon class="w-5 h-5 text-gray-600" />
        </div>
        <div class="text-sm">
          <div class="text-gray-500">May 2024</div>
          <div class="flex items-center gap-4">
            <div class="flex items-center">
              <div class="w-3 h-3 rounded-full bg-purple-600 mr-2"></div>
              <span>Income</span>
              <span class="font-semibold ml-2">${{ formatCurrency(2198.11) }}</span>
            </div>
            <div class="flex items-center">
              <div class="w-3 h-3 bg-blue-300 mr-2 rounded-full"></div>
              <span>Expense</span>
              <span class="font-semibold ml-2">${{ formatCurrency(733.43) }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="h-64">
      <Bar
        :data="chartData"
        :options="chartOptions"
      />
    </div>
  </div>
</template>

<script setup>
import { Bar } from 'vue-chartjs'
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend
} from 'chart.js'
import { ChevronRightIcon, CalendarIcon } from '@heroicons/vue/outline'

ChartJS.register(
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend
)

// Create diagonal pattern for expense bars
onMounted(() => {
  const canvas = document.createElement('canvas')
  const ctx = canvas.getContext('2d')
  canvas.width = 6
  canvas.height = 6
  ctx.strokeStyle = '#ffffff'
  ctx.lineWidth = 1
  ctx.beginPath()
  ctx.moveTo(0, 6)
  ctx.lineTo(6, 0)
  ctx.stroke()
  
  const pattern = ctx.createPattern(canvas, 'repeat')
  chartData.value.datasets[1].backgroundColor = pattern
})

const formatCurrency = (value) => {
  return new Intl.NumberFormat('en-US', {
    minimumFractionDigits: 2,
    maximumFractionDigits: 2
  }).format(value)
}

const chartData = ref({
  labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
  datasets: [
    {
      label: 'Income',
      data: [3000, 4000, 5000, 8000, 7000, 4000, 5000, 4000, 5000, 6000, 4000, 3000],
      backgroundColor: '#7C3AED', // Purple
      borderRadius: 4,
      barPercentage: 0.6,
    },
    {
      label: 'Expense',
      data: [1000, 1500, 2000, 3000, 2500, 1500, 2000, 1500, 2000, 2500, 1500, 1000],
      backgroundColor: '#93C5FD', // Light blue
      borderRadius: 4,
      barPercentage: 0.6,
    }
  ]
})

const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      display: false
    },
    tooltip: {
      backgroundColor: 'white',
      titleColor: '#6B7280',
      bodyColor: '#374151',
      borderColor: '#E5E7EB',
      borderWidth: 1,
      padding: 12,
      displayColors: true,
      callbacks: {
        label: function(context) {
          return `${context.dataset.label}: $${formatCurrency(context.raw)}`
        }
      }
    }
  },
  scales: {
    x: {
      stacked: true,
      grid: {
        display: false
      },
      ticks: {
        color: '#6B7280',
        font: {
          size: 12
        }
      }
    },
    y: {
      stacked: true,
      grid: {
        color: '#E5E7EB',
        borderDash: [2],
        drawBorder: false
      },
      ticks: {
        callback: value => `$${value/1000}k`,
        stepSize: 2000,
        color: '#6B7280',
        font: {
          size: 12
        }
      },
      beginAtZero: true
    }
  }
})
</script>

<style scoped>
:deep(.expense-pattern) {
  fill: url(#expensePattern);
}
</style>