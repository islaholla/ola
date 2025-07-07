<template>
  <div class="dashboard-container">
    <!-- Sidebar Navigation -->
    <Sidebar />

    <!-- Main Content Area -->
    <div class="main-content">
      <!-- Header -->
      <Header />

      <!-- Tables Section -->
      <main class="tables-main">
        <!-- First Row: Development Table and Check Table -->
        <div class="tables-row">
          <DevelopmentTable />
          <CheckTable />
        </div>

        <!-- Second Row: 4-Column Table and Complex Table -->
        <div class="tables-row">
          <FourColumnTable />
          <ComplexTable />
        </div>
      </main>

      <!-- Footer -->
      <Footer />
    </div>
  </div>
</template>

<script setup>
import Sidebar from "./components/Sidebar.vue";
import Header from "./components/Header.vue";
import DevelopmentTable from "./components/tables/DevelopmentTable.vue";
import CheckTable from "./components/tables/CheckTable.vue";
import FourColumnTable from "./components/tables/FourColumnTable.vue";
import ComplexTable from "./components/tables/ComplexTable.vue";
import Footer from "./components/Footer.vue";
</script>

<style scoped>
.dashboard-container {
  display: flex;
  min-height: 100vh;
  width: 100%;
  background: var(--secondary-grey-300);
}

.main-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  background: var(--secondary-grey-300);
  overflow-x: hidden;
}

.tables-main {
  flex: 1;
  padding: 0 30px 30px;
}

.tables-row {
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
  align-items: flex-start;
}

.tables-row:last-child {
  margin-bottom: 0;
}

@media (max-width: 1200px) {
  .tables-row {
    flex-direction: column;
    gap: 15px;
  }

  .tables-main {
    padding: 0 15px 15px;
  }
}

@media (max-width: 768px) {
  .dashboard-container {
    flex-direction: column;
  }

  .tables-main {
    padding: 0 10px 10px;
  }

  .tables-row {
    gap: 10px;
  }
}
</style>
