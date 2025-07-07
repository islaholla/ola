<template>
  <div class="table-card">
    <!-- Header -->
    <div class="table-header">
      <h2 class="table-title">Complex Table</h2>
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
          <div class="project-cell">
            <span class="project-name">{{ row.name }}</span>
          </div>
          <div class="status-cell">
            <div class="status-indicator" :class="getStatusClass(row.status)">
              <component :is="getStatusIcon(row.status)" />
              <span class="status-text">{{ row.status }}</span>
            </div>
          </div>
          <div class="date-cell">
            <span class="date-text">{{ row.date }}</span>
          </div>
          <div class="progress-cell">
            <div class="progress-bar-container">
              <div class="progress-bar">
                <div
                  class="progress-fill"
                  :style="{ width: row.percentage + '%' }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Status icon components
const ApprovedIcon = {
  template: `
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
      <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2ZM9.29 16.29L5.7 12.7C5.31 12.31 5.31 11.68 5.7 11.29C6.09 10.9 6.72 10.9 7.11 11.29L10 14.17L16.88 7.29C17.27 6.9 17.9 6.9 18.29 7.29C18.68 7.68 18.68 8.31 18.29 8.7L10.7 16.29C10.32 16.68 9.68 16.68 9.29 16.29Z" fill="#05CD99"/>
    </svg>
  `,
};

const DisableIcon = {
  template: `
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
      <path d="M12 2C6.47 2 2 6.47 2 12C2 17.53 6.47 22 12 22C17.53 22 22 17.53 22 12C22 6.47 17.53 2 12 2ZM16.3 16.3C15.91 16.69 15.28 16.69 14.89 16.3L12 13.41L9.11 16.3C8.72 16.69 8.09 16.69 7.7 16.3C7.31 15.91 7.31 15.28 7.7 14.89L10.59 12L7.7 9.11C7.31 8.72 7.31 8.09 7.7 7.7C8.09 7.31 8.72 7.31 9.11 7.7L12 10.59L14.89 7.7C15.28 7.31 15.91 7.31 16.3 7.7C16.69 8.09 16.69 8.72 16.3 9.11L13.41 12L16.3 14.89C16.68 15.27 16.68 15.91 16.3 16.3Z" fill="#EE5D50"/>
    </svg>
  `,
};

const ErrorIcon = {
  template: `
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
      <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2ZM13 17H11V15H13V17ZM13 13H11V7H13V13Z" fill="#FFCE20"/>
    </svg>
  `,
};

const tableData = ref([
  {
    name: "Marketplace",
    status: "Approved",
    date: "24.Jan.2021",
    percentage: 78,
  },
  {
    name: "Venus Dashboard Builder",
    status: "Disable",
    date: "30.Dec.2021",
    percentage: 42,
  },
  {
    name: "Venus Design System",
    status: "Error",
    date: "20.May.2021",
    percentage: 92,
  },
  {
    name: "Uranus",
    status: "Approved",
    date: "12.Jul.2021",
    percentage: 59,
  },
]);

const getStatusClass = (status) => {
  switch (status) {
    case "Approved":
      return "status-approved";
    case "Disable":
      return "status-disabled";
    case "Error":
      return "status-error";
    default:
      return "";
  }
};

const getStatusIcon = (status) => {
  switch (status) {
    case "Approved":
      return ApprovedIcon;
    case "Disable":
      return DisableIcon;
    case "Error":
      return ErrorIcon;
    default:
      return ApprovedIcon;
  }
};
</script>

<style scoped>
.table-card {
  background: var(--secondary-primary-white);
  border-radius: 20px;
  padding: 0;
  width: 100%;
  max-width: 796px;
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
  grid-template-columns: 1fr 160px 140px 150px;
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
  grid-template-columns: 1fr 160px 140px 150px;
  gap: 20px;
  align-items: center;
}

.project-cell {
  display: flex;
  align-items: center;
}

.project-name {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-900);
}

.status-cell {
  display: flex;
  align-items: center;
}

.status-indicator {
  display: flex;
  align-items: center;
  gap: 8px;
}

.status-text {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-900);
}

.date-cell {
  display: flex;
  align-items: center;
}

.date-text {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-900);
}

.progress-cell {
  display: flex;
  align-items: center;
}

.progress-bar-container {
  width: 108px;
}

.progress-bar {
  width: 100%;
  height: 8px;
  background: var(--secondary-dark-grey-100);
  border-radius: 21px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: var(--primary-purple-blue-500);
  border-radius: 21px;
  transition: width 0.3s ease;
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

  .progress-bar-container {
    width: 100%;
  }
}
</style>
