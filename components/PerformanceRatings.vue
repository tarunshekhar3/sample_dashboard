<!-- components/EmployeePerformanceChart.vue -->
<template>
  <div class="bg-white p-6 rounded-lg">
    <div class="flex justify-between items-center mb-6">
      <div>
        <h3 class="text-lg font-semibold">Employee Performance Ratings</h3>
        <div class="flex items-center mt-2">
          <span class="text-3xl font-bold">98%</span>
          <span class="text-sm text-gray-500 ml-4">
            At Tur Agency, we're proud of our employees' consistent punctuality and quality work
          </span>
        </div>
      </div>
      <button class="text-gray-400">
        <DotsHorizontalIcon class="w-5 h-5" />
      </button>
    </div>

    <!-- Performance Bars -->
    <div class="space-y-6">
      <div v-for="employee in employees" :key="employee.name" class="space-y-2">
        <div class="text-sm text-gray-600">{{ employee.name }}</div>
        <div class="flex gap-1">
          <!-- Task Completed -->
          <div 
            class="h-2 bg-purple-500 rounded-full"
            :style="{ width: `${employee.taskCompleted * 2}%` }"
          ></div>
          <!-- Presence -->
          <div 
            class="h-2 bg-blue-400 rounded-full"
            :style="{ width: `${employee.presence * 2}%` }"
          ></div>
          <!-- Completed Meeting -->
          <div 
            class="h-2 bg-teal-400 rounded-full"
            :style="{ width: `${employee.completedMeeting * 2}%` }"
          ></div>
        </div>
        <div class="text-xs text-gray-400">
          {{ employee.taskCompleted + employee.presence + employee.completedMeeting }} total points
        </div>
      </div>
    </div>

    <!-- Legend -->
    <div class="flex gap-6 mt-8">
      <div class="flex items-center gap-2">
        <div class="w-3 h-3 rounded-full bg-purple-500"></div>
        <span class="text-sm text-gray-600">Task completed</span>
      </div>
      <div class="flex items-center gap-2">
        <div class="w-3 h-3 rounded-full bg-blue-400"></div>
        <span class="text-sm text-gray-600">Presence</span>
      </div>
      <div class="flex items-center gap-2">
        <div class="w-3 h-3 rounded-full bg-teal-400"></div>
        <span class="text-sm text-gray-600">Completed Meeting</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { DotsHorizontalIcon } from '@heroicons/vue/outline'

const employees = ref([
  {
    name: 'Ahsan Tapadar',
    taskCompleted: 15,
    presence: 10,
    completedMeeting: 8
  },
  {
    name: 'Koyes Ahmed',
    taskCompleted: 18,
    presence: 12,
    completedMeeting: 10
  },
  {
    name: 'Washi Bin M.',
    taskCompleted: 25,
    presence: 8,
    completedMeeting: 12
  },
  {
    name: 'Mir Muhsin',
    taskCompleted: 12,
    presence: 10,
    completedMeeting: 8
  },
  {
    name: 'Turja Sen Das',
    taskCompleted: 20,
    presence: 15,
    completedMeeting: 14
  }
])
</script>

<style scoped>
/* Optional: Add transitions for smoother updates */
.h-2 {
  transition: width 0.3s ease-in-out;
}
</style>