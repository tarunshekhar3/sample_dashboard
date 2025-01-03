<template>
  <div>
    <!-- Toggle Button -->
    <button
      class="md:hidden fixed top-4 left-4 z-50 bg-purple-600 text-white px-4 py-2 rounded-md"
      @click="isOpen = !isOpen"
    >
      Menu
    </button>

    <!-- Sidebar -->
    <div
      :class="[
        'fixed inset-y-0 left-0 w-64 bg-gray-100 p-4 transition-transform',
        isOpen ? 'translate-x-0' : '-translate-x-full',
        'md:static md:translate-x-0',
      ]"
    >
      <ul>
        <li v-for="item in menuItems" :key="item.name" class="mb-2">
          <NuxtLink
            :to="item.path"
            class="text-gray-700 hover:text-purple-600 block"
          >
            {{ item.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isOpen = ref(false);
const menuItems = [
  { name: 'Dashboard', path: '/' },
  { name: 'Projects', path: '/projects' },
  { name: 'Calendar', path: '/calendar' },
  { name: 'Leave Management', path: '/leave' },
];
</script>
