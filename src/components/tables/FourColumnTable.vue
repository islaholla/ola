<template>
  <div class="table-card">
    <!-- Header -->
    <div class="table-header">
      <h2 class="table-title">4-Column Table</h2>
      <button class="more-btn">
        <svg class="more-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M6 10C4.9 10 4 10.9 4 12C4 13.1 4.9 14 6 14C7.1 14 8 13.1 8 12C8 10.9 7.1 10 6 10ZM18 10C16.9 10 16 10.9 16 12C16 13.1 16.9 14 18 14C19.1 14 20 13.1 20 12C20 10.9 19.1 10 18 10ZM12 10C10.9 10 10 10.9 10 12C10 13.1 10.9 14 12 14C13.1 14 14 13.1 14 12C14 10.9 13.1 10 12 10Z"
            fill="#4318FF"
          />
        </svg>
      </button>
    </div>

    <!-- Column Headers -->
    <div class="table-columns">
      <div class="column-header">
        <span class="column-title">Title</span>
        <svg class="sort-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M8.11997 9.29L12 13.17L15.88 9.29C16.27 8.9 16.9 8.9 17.29 9.29C17.68 9.68 17.68 10.31 17.29 10.7L12.7 15.29C12.31 15.68 11.68 15.68 11.29 15.29L6.69997 10.7C6.30997 10.31 6.30997 9.68 6.69997 9.29C7.08997 8.91 7.72997 8.9 8.11997 9.29Z"
            fill="#A3AED0"
          />
        </svg>
      </div>
      <div class="column-header">
        <span class="column-title">Title</span>
        <svg class="sort-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M8.11997 9.29L12 13.17L15.88 9.29C16.27 8.9 16.9 8.9 17.29 9.29C17.68 9.68 17.68 10.31 17.29 10.7L12.7 15.29C12.31 15.68 11.68 15.68 11.29 15.29L6.69997 10.7C6.30997 10.31 6.30997 9.68 6.69997 9.29C7.08997 8.91 7.72997 8.9 8.11997 9.29Z"
            fill="#A3AED0"
          />
        </svg>
      </div>
      <div class="column-header">
        <span class="column-title">Title</span>
        <svg class="sort-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M8.11997 9.29L12 13.17L15.88 9.29C16.27 8.9 16.9 8.9 17.29 9.29C17.68 9.68 17.68 10.31 17.29 10.7L12.7 15.29C12.31 15.68 11.68 15.68 11.29 15.29L6.69997 10.7C6.30997 10.31 6.30997 9.68 6.69997 9.29C7.08997 8.91 7.72997 8.9 8.11997 9.29Z"
            fill="#A3AED0"
          />
        </svg>
      </div>
      <div class="column-header">
        <span class="column-title">Title</span>
        <svg class="sort-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M8.11997 9.29L12 13.17L15.88 9.29C16.27 8.9 16.9 8.9 17.29 9.29C17.68 9.68 17.68 10.31 17.29 10.7L12.7 15.29C12.31 15.68 11.68 15.68 11.29 15.29L6.69997 10.7C6.30997 10.31 6.30997 9.68 6.69997 9.29C7.08997 8.91 7.72997 8.9 8.11997 9.29Z"
            fill="#A3AED0"
          />
        </svg>
      </div>
    </div>

    <!-- Table Data -->
    <div class="table-body">
      <div v-for="(row, index) in tableData" :key="index" class="table-row">
        <div class="row-content">
          <div class="data-cell">
            <span class="data-text">{{ row.name }}</span>
          </div>
          <div class="data-cell">
            <span class="data-text">{{ row.percentage }}%</span>
          </div>
          <div class="data-cell">
            <span class="data-text">{{ row.value }}</span>
          </div>
          <div class="data-cell">
            <span class="data-text">{{ row.date }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const tableData = ref([
  {
    name: "Marketplace",
    percentage: "17.5",
    value: "2.458",
    date: "24.Jan.2021",
  },
  {
    name: "Venus PRO",
    percentage: "10.8",
    value: "1.485",
    date: "12.Jun.2021",
  },
  {
    name: "Uranus Kit",
    percentage: "21.3",
    value: "1.024",
    date: "5.Jan.2021",
  },
  {
    name: "Venus DS",
    percentage: "31.5",
    value: "858",
    date: "7.Mar.2021",
  },
  {
    name: "Venus 3D Asset",
    percentage: "12.2",
    value: "258",
    date: "17.Dec.2021",
  },
]);
</script>

<style scoped>
.table-card {
  background: var(--secondary-primary-white);
  border-radius: 20px;
  padding: 0;
  width: 100%;
  max-width: 774px;
}

.table-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 19px 31px;
}

.table-title {
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
  letter-spacing: -0.48px;
  color: var(--secondary-grey-900);
  margin: 0;
}

.more-btn {
  width: 37px;
  height: 37px;
  background: var(--secondary-grey-300);
  border: none;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.2s ease;
}

.more-btn:hover {
  background: #e0e7f0;
}

.more-icon {
  width: 24px;
  height: 24px;
}

.table-columns {
  display: grid;
  grid-template-columns: 1fr 120px 120px 140px;
  gap: 20px;
  padding: 0 31px;
  border-bottom: 1px solid var(--secondary-grey-400);
  padding-bottom: 12px;
  margin-bottom: 20px;
}

.column-header {
  display: flex;
  align-items: center;
  gap: 7px;
}

.column-title {
  font-size: 14px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-600);
}

.sort-icon {
  width: 24px;
  height: 24px;
}

.table-body {
  padding: 0 31px 31px;
}

.table-row {
  margin-bottom: 20px;
}

.table-row:last-child {
  margin-bottom: 0;
}

.row-content {
  display: grid;
  grid-template-columns: 1fr 120px 120px 140px;
  gap: 20px;
  align-items: center;
}

.data-cell {
  display: flex;
  align-items: center;
}

.data-text {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-900);
}

@media (max-width: 768px) {
  .table-columns,
  .row-content {
    grid-template-columns: 1fr;
    gap: 10px;
  }

  .table-header {
    padding: 15px 20px;
  }

  .table-columns {
    padding: 0 20px;
  }

  .table-body {
    padding: 0 20px 20px;
  }

  .table-title {
    font-size: 20px;
  }

  .row-content {
    background: var(--secondary-grey-300);
    padding: 15px;
    border-radius: 12px;
  }
}
</style>
