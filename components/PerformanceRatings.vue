<template>
    <div class="bg-white p-4 rounded-lg shadow-md">
      <h2 class="text-lg font-bold mb-2">Employee Performance Ratings</h2>
      <ul>
        <li v-for="employee in employees" :key="employee.id" class="mb-2">
          <p>{{ employee.name }}: <span class="text-purple-600 font-bold">{{ employee.rating }}%</span></p>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  const employees = [
    { id: 1, name: 'Ahsan Tapadar', rating: 98 },
    { id: 2, name: 'Keyes Ahmed', rating: 92 },
    { id: 3, name: 'Washi Bin M', rating: 95 },
  ];
  </script>
  