<template>
  <div class="bg-white p-4 rounded-lg shadow-md overflow-x-auto">
    <h2 class="text-lg font-bold mb-4">All Employees</h2>
    <table class="table-auto w-full text-left border-collapse">
      <thead>
        <tr>
          <th class="border-b p-2">ID</th>
          <th class="border-b p-2">Name</th>
          <th class="border-b p-2">Role</th>
          <th class="border-b p-2">Status</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td class="p-2 border-b">{{ employee.id }}</td>
          <td class="p-2 border-b">{{ employee.name }}</td>
          <td class="p-2 border-b">{{ employee.role }}</td>
          <td class="p-2 border-b">{{ employee.status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
const employees = ref([
  { id: 1, name: 'John Doe', role: 'Software Engineer', status: 'Active' },
  { id: 2, name: 'Jane Doe', role: 'Product Manager', status: 'Active' },
  { id: 3, name: 'Alice', role: 'Designer', status: 'Inactive' },
  { id: 4, name: 'Bob', role: 'QA Engineer', status: 'Active' },
]);
</script>