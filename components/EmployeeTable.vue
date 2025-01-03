<template>
  <div class="bg-white p-4 rounded-lg shadow-md overflow-x-auto">
    <h2 class="text-lg font-bold mb-4">All Employees</h2>
    <table class="table-auto w-full text-left border-collapse">
      <thead class="bg-gray-50">
        <tr>
          <th class="border-b p-2">ID</th>
          <th class="border-b p-2">Name</th>
          <th class="border-b p-2">Email</th>
          <th class="border-b p-2">Role</th>
          <th class="border-b p-2">Status</th>
        </tr>
      </thead>
      <tbody class="bg-white divide-y divide-gray-200">
        <tr v-for="employee in employees" :key="employee.id">
          <td class="p-2 border-b">{{ employee.id }}</td>
          <td class="p-2 border-b">{{ employee.name }}</td>
          <td class="p-2 border-b">{{ employee.email }}</td>
          <td class="p-2 border-b">{{ employee.role }}</td>
          <td class="p-2 border-b">{{ employee.status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>

const employees = [
  {
    id: 'TUR877219',
    name: 'Ahsan Tapadar',
    email: 'ahsan.tur@mail.com',
    role: 'Sr UI/UX Designer',
    department: 'Team Projects',
    status: 'Full-time'
  },
  {
    id: 'TUR185103',
    name: 'Washi Bin M.',
    email: 'washi.tur@mail.com',
    role: 'Lead Product Designer',
    department: 'Head of Projects',
    status: 'Full-time'
  },
  {
    id: 'TUR715481',
    name: 'Koyes Ahmed',
    email: 'koyes.tur@mail.com',
    role: 'Sr UX Designer',
    department: 'Client & Team Work',
    status: 'Full-time'
  },
  {
    id: 'TUR016481',
    name: 'Turja Sen Das',
    email: 'turja.tur@mail.com',
    role: 'Mid UI Designer',
    department: 'Case Study',
    status: 'Freelance'
  }
];
</script>
