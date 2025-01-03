<template>
  <div class="flex flex-col md:flex-row">
    <Sidebar />
    <div class="flex-grow p-6">
      <Header />
      <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-4 mt-6">
        <AttendanceOverview />
        <PerformanceRatings />
        <EmployeeTable />
      </div>
    </div>
  </div>
</template>

