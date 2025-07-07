<template>
  <div class="table-card">
    <!-- Header -->
    <div class="table-header">
      <h2 class="table-title">Development Table</h2>
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
          <div class="project-info">
            <span class="project-name">{{ row.name }}</span>
          </div>
          <div class="platform-icons">
            <div
              v-for="platform in row.platforms"
              :key="platform"
              class="platform-icon"
            >
              <component :is="getPlatformIcon(platform)" />
            </div>
          </div>
          <div class="date-cell">
            <span class="date-text">{{ row.date }}</span>
          </div>
          <div class="progress-cell">
            <span class="percentage">{{ row.percentage }}%</span>
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
</template>

<script setup>
import { ref } from "vue";

// Platform icon components as string templates
const AndroidIcon = {
  template: `
    <svg width="16" height="18" viewBox="0 0 16 18" fill="none">
      <path d="M4.90269 0.425728C4.87644 0.425984 4.85198 0.432465 4.82786 0.445253C4.74868 0.48725 4.72264 0.574313 4.76664 0.65027L5.5489 2.0024C4.04387 2.75169 3.02731 4.17563 3.02527 5.80985H12.9293C12.9273 4.17563 11.9107 2.75169 10.4057 2.0024L11.188 0.65027C11.232 0.574313 11.2059 0.48725 11.1267 0.445253C11.1026 0.432465 11.0782 0.425967 11.0519 0.425728C10.9957 0.425209 10.9424 0.452074 10.9125 0.503829L10.12 1.87061C9.47174 1.59548 8.74461 1.44105 7.9773 1.44105C7.20999 1.44105 6.48286 1.59548 5.83459 1.87061L5.04213 0.503829C5.01215 0.452074 4.95888 0.425212 4.90269 0.425728ZM3.02527 6.18409V13.0521C3.02527 13.6867 3.55922 14.1976 4.22246 14.1976H11.7321C12.3954 14.1976 12.9293 13.6867 12.9293 13.0521V6.18409H3.02527Z" fill="#E0E5F2"/>
      <path d="M5.6918 3.28467C5.46571 3.28467 5.27856 3.46373 5.27856 3.68006C5.27856 3.89638 5.46571 4.07544 5.6918 4.07544C5.91789 4.07544 6.10504 3.89638 6.10504 3.68006C6.10504 3.46373 5.91789 3.28467 5.6918 3.28467ZM10.2629 3.28467C10.0368 3.28467 9.84967 3.46373 9.84967 3.68006C9.84967 3.89638 10.0368 4.07544 10.2629 4.07544C10.489 4.07544 10.6761 3.89638 10.6761 3.68006C10.6761 3.46373 10.489 3.28467 10.2629 3.28467Z" fill="white"/>
    </svg>
  `,
};

const WindowsIcon = {
  template: `
    <svg width="19" height="18" viewBox="0 0 19 18" fill="none">
      <path d="M0 2.53677L7.70515 1.54264L7.70852 8.58371L0.00703864 8.62526L0 2.53677ZM7.70148 9.39498L7.70746 16.4422L0.00598068 15.4391L0.00554886 9.34771L7.70148 9.39498ZM8.63552 1.41259L18.8519 0V8.49416L8.63552 8.571V1.41259ZM18.8543 9.46125L18.8519 17.9172L8.6355 16.5511L8.62119 9.44542L18.8543 9.46125Z" fill="#E0E5F2"/>
    </svg>
  `,
};

const AppleIcon = {
  template: `
    <svg width="15" height="18" viewBox="0 0 15 18" fill="none">
      <path d="M12.5059 17.28C11.5404 18.2268 10.4751 18.0792 9.45963 17.6328C8.38006 17.1774 7.39312 17.1486 6.25298 17.6328C4.83314 18.252 4.07958 18.072 3.22447 17.28C-1.60332 12.258 -0.890729 4.60803 4.59621 4.32003C5.92697 4.39203 6.85868 5.06343 7.64253 5.11923C8.80761 4.87983 9.92281 4.19403 11.1698 4.28403C12.6681 4.40643 13.7886 5.00403 14.5368 6.07863C11.4549 7.95063 12.1853 12.0546 15.016 13.2066C14.4495 14.7096 13.7227 16.1946 12.5042 17.2926L12.5059 17.28ZM7.53564 4.26603C7.39134 2.03403 9.18172 0.198036 11.2411 0.0180359C11.5244 2.59203 8.92519 4.51803 7.53564 4.26603Z" fill="#E0E5F2"/>
    </svg>
  `,
};

const tableData = ref([
  {
    name: "Marketplace",
    platforms: ["apple", "android", "windows"],
    date: "12.Jan.2021",
    percentage: 75.5,
  },
  {
    name: "Venus DB PRO",
    platforms: ["apple"],
    date: "21.Feb.2021",
    percentage: 35.4,
  },
  {
    name: "Venus DS",
    platforms: ["apple", "android", "windows"],
    date: "13.Mar.2021",
    percentage: 25,
  },
  {
    name: "Venus 3D Asset",
    platforms: ["apple", "windows"],
    date: "24.Jan.2021",
    percentage: 100,
  },
  {
    name: "Uranus",
    platforms: ["android", "windows"],
    date: "21.Sep.2021",
    percentage: 12.2,
  },
]);

const getPlatformIcon = (platform) => {
  switch (platform) {
    case "android":
      return AndroidIcon;
    case "windows":
      return WindowsIcon;
    case "apple":
      return AppleIcon;
    default:
      return AndroidIcon;
  }
};
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
  grid-template-columns: 1fr 180px 120px 120px;
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
  grid-template-columns: 1fr 180px 120px 120px;
  gap: 20px;
  align-items: center;
}

.project-info {
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

.platform-icons {
  display: flex;
  gap: 8px;
  align-items: center;
}

.platform-icon {
  width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
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
  flex-direction: column;
  gap: 4px;
}

.percentage {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-900);
}

.progress-bar {
  width: 63px;
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

  .progress-cell {
    flex-direction: row;
    align-items: center;
    gap: 10px;
  }
}
</style>
