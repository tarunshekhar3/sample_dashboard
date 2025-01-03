<template>
  <div class="flex flex-col md:flex-row min-h-screen">
    <!-- Sidebar -->
    <Sidebar />

    <!-- Main Content -->
    <div class="flex-grow p-4 md:p-6 bg-gray-100">
      <!-- Header -->
      <Header />

      <!-- First Grid (Top Section) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-4 mt-6">
        <TotalEmployees />
        <AttendanceOverview />
        <TotalUsedDevices />
      </div>

      <!-- Second Grid (Middle Section) -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-6">
        <PerformanceRatings />
        <IncomeStatistics />
      </div>

      <!-- Third Grid (Bottom Section) -->
      <div class="grid grid-cols-1 gap-4 mt-6">
        <EmployeeTable />
      </div>
    </div>
  </div>
</template>
