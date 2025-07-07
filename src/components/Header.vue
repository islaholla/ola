<template>
  <header class="header">
    <!-- Breadcrumb and Title -->
    <div class="header-content">
      <div class="breadcrumb">
        <span class="breadcrumb-text">Pages / Tables</span>
      </div>
      <h1 class="page-title">Tables</h1>
    </div>

    <!-- Header Controls -->
    <div class="header-controls">
      <!-- Search Input -->
      <div class="search-container">
        <div class="search-input">
          <svg class="search-icon" viewBox="0 0 10 10" fill="none">
            <circle cx="5" cy="5" r="4.3" stroke="#2B3674" stroke-width="1.4" />
            <path
              d="M8 8L8.5 8.5"
              stroke="#2B3674"
              stroke-width="1.4"
              stroke-linecap="round"
            />
          </svg>
          <input type="text" placeholder="Search" class="search-field" />
        </div>
      </div>

      <!-- Control Icons -->
      <div class="control-icons">
        <!-- Notifications -->
        <button class="control-btn">
          <svg class="control-icon" viewBox="0 0 24 24" fill="none">
            <path
              d="M19.29 17.29L18 16V11C18 7.93 16.36 5.36 13.5 4.68V4C13.5 3.17 12.83 2.5 12 2.5C11.17 2.5 10.5 3.17 10.5 4V4.68C7.62999 5.36 5.99999 7.92 5.99999 11V16L4.70999 17.29C4.07999 17.92 4.51999 19 5.40999 19H18.58C19.48 19 19.92 17.92 19.29 17.29ZM16 17H7.99999V11C7.99999 8.52 9.50999 6.5 12 6.5C14.49 6.5 16 8.52 16 11V17ZM12 22C13.1 22 14 21.1 14 20H9.99999C9.99999 21.1 10.89 22 12 22Z"
              fill="#A3AED0"
            />
          </svg>
        </button>

        <!-- Dark Mode Toggle -->
        <button class="control-btn">
          <svg
            class="control-icon"
            width="18"
            height="18"
            viewBox="0 0 18 18"
            fill="none"
          >
            <path
              d="M9.95691 18C12.7329 18 15.2683 16.737 16.948 14.6675C17.1965 14.3613 16.9255 13.9141 16.5415 13.9872C12.175 14.8188 8.1651 11.4709 8.1651 7.06303C8.1651 4.52398 9.52431 2.18914 11.7334 0.931992C12.0739 0.738211 11.9883 0.221941 11.6013 0.150469C11.0589 0.0504468 10.5085 8.21369e-05 9.95691 0C4.98902 0 0.956909 4.02578 0.956909 9C0.956909 13.9679 4.98269 18 9.95691 18Z"
              fill="#A3AED0"
            />
          </svg>
        </button>

        <!-- Info -->
        <button class="control-btn">
          <svg class="control-icon" viewBox="0 0 24 24" fill="none">
            <path
              d="M11 7H13V9H11V7ZM12 17C12.55 17 13 16.55 13 16V12C13 11.45 12.55 11 12 11C11.45 11 11 11.45 11 12V16C11 16.55 11.45 17 12 17ZM12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2ZM12 20C7.59 20 4 16.41 4 12C4 7.59 7.59 4 12 4C16.41 4 20 7.59 20 12C20 16.41 16.41 20 12 20Z"
              fill="#A3AED0"
            />
          </svg>
        </button>

        <!-- User Avatar -->
        <div class="user-avatar">
          <div class="avatar-circle">
            <img
              src="https://cdn.builder.io/api/v1/image/assets%2Fcf620419baba4e78896e3ddb8eb284f9%2Ffe95a94513674c3fb8fbc89c25c72f93?format=webp&width=41"
              alt="User Avatar"
              class="avatar-img"
            />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  padding: 49px 30px 0;
  background: var(--secondary-grey-300);
  min-height: 97px;
}

.header-content {
  display: flex;
  flex-direction: column;
}

.breadcrumb {
  margin-bottom: 2px;
}

.breadcrumb-text {
  font-size: 14px;
  font-weight: 500;
  line-height: 24px;
  color: var(--secondary-grey-700);
}

.page-title {
  font-size: 34px;
  font-weight: 700;
  line-height: 42px;
  letter-spacing: -0.68px;
  color: var(--secondary-grey-900);
  margin: 0;
}

.header-controls {
  display: flex;
  align-items: center;
  gap: 20px;
  background: var(--secondary-primary-white);
  border-radius: 30px;
  padding: 10px;
  box-shadow: 14px 17px 40px 4px rgba(112, 144, 176, 0.08);
}

.search-container {
  flex: 1;
}

.search-input {
  display: flex;
  align-items: center;
  background: var(--secondary-grey-300);
  border-radius: 49px;
  padding: 10px 20px;
  min-width: 214px;
}

.search-icon {
  width: 11px;
  height: 11px;
  margin-right: 12px;
  flex-shrink: 0;
}

.search-field {
  border: none;
  background: transparent;
  outline: none;
  font-size: 14px;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: -0.28px;
  color: var(--secondary-dark-grey-500);
  flex: 1;
}

.search-field::placeholder {
  color: var(--secondary-dark-grey-500);
}

.control-icons {
  display: flex;
  align-items: center;
  gap: 20px;
}

.control-btn {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: opacity 0.2s ease;
}

.control-btn:hover {
  opacity: 0.7;
}

.control-icon {
  width: 24px;
  height: 24px;
}

.user-avatar {
  margin-left: 10px;
}

.avatar-circle {
  width: 41px;
  height: 41px;
  border-radius: 50%;
  overflow: hidden;
  background: var(--primary-purple-blue-500);
  display: flex;
  align-items: center;
  justify-content: center;
}

.avatar-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 1024px) {
  .header {
    flex-direction: column;
    gap: 20px;
    align-items: stretch;
  }

  .header-controls {
    flex-direction: column;
    align-items: stretch;
    gap: 15px;
  }

  .control-icons {
    justify-content: center;
  }

  .search-input {
    min-width: auto;
  }
}

@media (max-width: 768px) {
  .header {
    padding: 20px 15px 0;
  }

  .page-title {
    font-size: 28px;
    line-height: 36px;
  }

  .header-controls {
    padding: 8px;
  }

  .search-input {
    padding: 8px 15px;
  }

  .control-icons {
    gap: 15px;
  }
}
</style>
