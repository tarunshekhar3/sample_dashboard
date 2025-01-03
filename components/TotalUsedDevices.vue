<template>
  <div class="bg-white p-6 rounded-lg shadow">
    <div class="flex justify-between items-center mb-4">
      <h3 class="font-semibold">Today Used Devices</h3>
      <DotsHorizontalIcon class="w-5 h-5 text-gray-400" />
    </div>
    <div class="flex justify-between items-center">
      <div class="relative w-32 h-32">
        <div class="text-center mt-12">
          <span class="text-3xl font-bold">100</span>
          <p class="text-sm text-gray-500">Overall</p>
        </div>
      </div>
      <div class="space-y-2">
        <div class="flex items-center gap-2">
          <span class="text-blue-500">80</span>
          <span>Macbook</span>
        </div>
        <div class="flex items-center gap-2">
          <span class="text-yellow-500">13</span>
          <span>Keyboard</span>
        </div>
        <div class="flex items-center gap-2">
          <span class="text-purple-500">07</span>
          <span>Headphones</span>
        </div>
      </div>
    </div>
  </div>
</template>
