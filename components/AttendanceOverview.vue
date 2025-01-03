<template>
  <div class="bg-white p-6 rounded-lg shadow">
    <div class="flex justify-between items-center mb-4">
      <h3 class="font-semibold">Attendance Overview</h3>
      <DotsHorizontalIcon class="w-5 h-5 text-gray-400" />
    </div>
    <div class="space-y-4">
      <div class="flex justify-between items-center">
        <span class="text-3xl font-bold">90%</span>
        <span class="text-green-500">+20% since last month</span>
      </div>
      <div class="h-2 bg-gray-100 rounded-full overflow-hidden">
        <div class="h-full bg-green-500 w-[60%]"></div>
        <div class="h-full bg-yellow-500 w-[20%] -mt-2"></div>
        <div class="h-full bg-purple-500 w-[10%] -mt-2"></div>
      </div>
      <div class="flex gap-4 text-sm">
        <span class="flex items-center gap-1">
          <div class="w-2 h-2 bg-yellow-500 rounded-full"></div>
          Sick Leave
        </span>
        <span class="flex items-center gap-1">
          <div class="w-2 h-2 bg-purple-500 rounded-full"></div>
          Day Off
        </span>
        <span class="flex items-center gap-1">
          <div class="w-2 h-2 bg-green-500 rounded-full"></div>
          On time
        </span>
      </div>
    </div>
  </div>
</template>
