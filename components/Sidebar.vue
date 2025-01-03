<template>
  <div class="flex h-screen bg-gray-100">
    <!-- Static Sidebar -->
    <aside class="w-64 bg-white shadow-lg p-4">
      <div class="flex items-center gap-2 mb-8">
        <div class="w-8 h-8 bg-purple-600 rounded-lg text-white flex items-center justify-center">
          TH
        </div>
        <span class="font-semibold text-lg">TurHR</span>
      </div>

      <!-- Navigation Links -->
      <nav class="space-y-2">
        <a
          href="#"
          class="flex items-center gap-3 px-4 py-2 text-purple-600 bg-purple-50 rounded-lg"
        >
          <HomeIcon class="w-5 h-5" />
          Dashboard
        </a>
        <template v-for="item in menuItems" :key="item.name">
          <a
            href="#"
            class="flex items-center gap-3 px-4 py-2 text-gray-600 hover:bg-gray-50 rounded-lg"
          >
            <component :is="item.icon" class="w-5 h-5" />
            {{ item.name }}
          </a>
        </template>
      </nav>
    </aside>

  </div>
</template>

<script setup>
import {
  HomeIcon,
  CalendarIcon,
  CogIcon,
  BellIcon,
  QuestionMarkCircleIcon,
  DocumentIcon,
} from "@heroicons/vue/outline";

// Static menu items
const menuItems = [
  { name: "Projects", icon: DocumentIcon },
  { name: "Calendar", icon: CalendarIcon },
  { name: "Leave Management", icon: CalendarIcon },
  { name: "Settings", icon: CogIcon },
  { name: "Notification", icon: BellIcon },
  { name: "Help & Center", icon: QuestionMarkCircleIcon },
];
</script>

<style scoped>
/* Add any additional styling as needed */
</style>
