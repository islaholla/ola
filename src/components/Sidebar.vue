<template>
  <div class="sidebar">
    <!-- Logo -->
    <div class="logo-section">
      <h1 class="logo-text">
        <span class="logo-primary">HORIZON</span>
        <span class="logo-secondary">FREE</span>
      </h1>
    </div>

    <!-- Separator -->
    <div class="separator"></div>

    <!-- Navigation Pages -->
    <nav class="navigation">
      <div class="nav-item active">
        <svg class="nav-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M9.99998 19V14H14V19C14 19.55 14.45 20 15 20H18C18.55 20 19 19.55 19 19V12H20.7C21.16 12 21.38 11.43 21.03 11.13L12.67 3.59997C12.29 3.25997 11.71 3.25997 11.33 3.59997L2.96998 11.13C2.62998 11.43 2.83998 12 3.29998 12H4.99998V19C4.99998 19.55 5.44998 20 5.99998 20H8.99998C9.54998 20 9.99998 19.55 9.99998 19Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">Dashboard</span>
        <div class="active-indicator"></div>
      </div>

      <div class="nav-item">
        <svg class="nav-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M15.55 13C16.3 13 16.96 12.59 17.3 11.97L20.88 5.48C21.25 4.82 20.77 4 20.01 4H5.21L4.27 2H1V4H3L6.6 11.59L5.25 14.03C4.52 15.37 5.48 17 7 17H19V15H7L8.1 13H15.55ZM6.16 6H18.31L15.55 11H8.53L6.16 6ZM7 18C5.9 18 5.01 18.9 5.01 20C5.01 21.1 5.9 22 7 22C8.1 22 9 21.1 9 20C9 18.9 8.1 18 7 18ZM17 18C15.9 18 15.01 18.9 15.01 20C15.01 21.1 15.9 22 17 22C18.1 22 19 21.1 19 20C19 18.9 18.1 18 17 18Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">NFT Marketplace</span>
      </div>

      <div class="nav-item">
        <svg
          class="nav-icon"
          width="28"
          height="28"
          viewBox="0 0 28 28"
          fill="none"
        >
          <path
            d="M7.46671 10.7333H7.70004C8.59837 10.7333 9.33337 11.4683 9.33337 12.3667V20.5333C9.33337 21.4317 8.59837 22.1667 7.70004 22.1667H7.46671C6.56837 22.1667 5.83337 21.4317 5.83337 20.5333V12.3667C5.83337 11.4683 6.56837 10.7333 7.46671 10.7333ZM14 5.83334C14.8984 5.83334 15.6334 6.56834 15.6334 7.46668V20.5333C15.6334 21.4317 14.8984 22.1667 14 22.1667C13.1017 22.1667 12.3667 21.4317 12.3667 20.5333V7.46668C12.3667 6.56834 13.1017 5.83334 14 5.83334ZM20.5334 15.1667C21.4317 15.1667 22.1667 15.9017 22.1667 16.8V20.5333C22.1667 21.4317 21.4317 22.1667 20.5334 22.1667C19.635 22.1667 18.9 21.4317 18.9 20.5333V16.8C18.9 15.9017 19.635 15.1667 20.5334 15.1667Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">Tables</span>
      </div>

      <div class="nav-item">
        <svg class="nav-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M4 13H10C10.55 13 11 12.55 11 12V4C11 3.45 10.55 3 10 3H4C3.45 3 3 3.45 3 4V12C3 12.55 3.45 13 4 13ZM4 21H10C10.55 21 11 20.55 11 20V16C11 15.45 10.55 15 10 15H4C3.45 15 3 15.45 3 16V20C3 20.55 3.45 21 4 21ZM14 21H20C20.55 21 21 20.55 21 20V12C21 11.45 20.55 11 20 11H14C13.45 11 13 11.45 13 12V20C13 20.55 13.45 21 14 21ZM13 4V8C13 8.55 13.45 9 14 9H20C20.55 9 21 8.55 21 8V4C21 3.45 20.55 3 20 3H14C13.45 3 13 3.45 13 4Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">Kanban</span>
      </div>

      <div class="nav-item">
        <svg class="nav-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M12 12C14.21 12 16 10.21 16 8C16 5.79 14.21 4 12 4C9.79 4 8 5.79 8 8C8 10.21 9.79 12 12 12ZM12 14C9.33 14 4 15.34 4 18V19C4 19.55 4.45 20 5 20H19C19.55 20 20 19.55 20 19V18C20 15.34 14.67 14 12 14Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">Profile</span>
      </div>

      <div class="nav-item">
        <svg class="nav-icon" viewBox="0 0 24 24" fill="none">
          <path
            d="M18 8H17V6C17 3.24 14.76 1 12 1C9.24 1 7 3.24 7 6V8H6C4.9 8 4 8.9 4 10V20C4 21.1 4.9 22 6 22H18C19.1 22 20 21.1 20 20V10C20 8.9 19.1 8 18 8ZM12 17C10.9 17 10 16.1 10 15C10 13.9 10.9 13 12 13C13.1 13 14 13.9 14 15C14 16.1 13.1 17 12 17ZM9 8V6C9 4.34 10.34 3 12 3C13.66 3 15 4.34 15 6V8H9Z"
            fill="currentColor"
          />
        </svg>
        <span class="nav-text">Sign In</span>
      </div>
    </nav>

    <!-- Get PRO CTA -->
    <div class="pro-cta">
      <div class="pro-icon">
        <svg width="94" height="94" viewBox="0 0 94 94" fill="none">
          <circle
            cx="47"
            cy="47"
            r="47"
            fill="url(#gradient)"
            stroke="white"
            stroke-width="5"
          />
          <defs>
            <linearGradient id="gradient" x1="0" y1="0" x2="94" y2="94">
              <stop stop-color="#868CFF" />
              <stop offset="1" stop-color="#4318FF" />
            </linearGradient>
          </defs>
        </svg>
      </div>
      <h3 class="pro-title">Upgrade to PRO</h3>
      <p class="pro-description">
        to get access to all features! Connect with Venus World!
      </p>
    </div>
  </div>
</template>

<style scoped>
.sidebar {
  width: 290px;
  height: 100vh;
  background: var(--secondary-primary-white);
  display: flex;
  flex-direction: column;
  position: relative;
}

.logo-section {
  padding: 56px 54px 0;
  margin-bottom: 48px;
}

.logo-text {
  font-family: "Poppins", sans-serif;
  font-size: 26px;
  line-height: 100%;
  margin: 0;
}

.logo-primary {
  font-weight: 700;
  color: var(--secondary-grey-900);
}

.logo-secondary {
  font-weight: 400;
  color: var(--secondary-grey-900);
}

.separator {
  width: 100%;
  height: 1px;
  background: var(--secondary-grey-300);
  margin-bottom: 38px;
}

.navigation {
  padding: 0 31px;
  flex: 1;
}

.nav-item {
  display: flex;
  align-items: center;
  padding: 6px 0;
  margin-bottom: 20px;
  position: relative;
  cursor: pointer;
  transition: all 0.2s ease;
}

.nav-item:hover {
  opacity: 0.8;
}

.nav-item.active .nav-text {
  color: var(--secondary-grey-900);
  font-weight: 700;
}

.nav-item.active .nav-icon {
  color: var(--primary-purple-blue-500);
}

.nav-icon {
  width: 24px;
  height: 24px;
  margin-right: 12px;
  color: var(--secondary-grey-600);
  transition: color 0.2s ease;
}

.nav-text {
  font-size: 16px;
  font-weight: 500;
  line-height: 30px;
  letter-spacing: -0.32px;
  color: var(--secondary-grey-600);
  transition: all 0.2s ease;
}

.active-indicator {
  position: absolute;
  right: -31px;
  top: 0;
  width: 4px;
  height: 36px;
  background: var(--primary-purple-blue-500);
  border-radius: 25px;
}

.pro-cta {
  margin: 0 31px 31px;
  padding: 24px;
  background: var(--gradients-gradient-style-1);
  border-radius: 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.pro-icon {
  position: absolute;
  top: -48px;
  left: 50%;
  transform: translateX(-50%);
  width: 94px;
  height: 94px;
}

.pro-title {
  font-size: 16px;
  font-weight: 700;
  line-height: 28px;
  letter-spacing: -0.32px;
  color: var(--secondary-primary-white);
  margin: 48px 0 8px;
}

.pro-description {
  font-size: 14px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: #e9edf7;
  margin: 0;
}

@media (max-width: 768px) {
  .sidebar {
    width: 100%;
    position: fixed;
    top: 0;
    left: -100%;
    z-index: 1000;
    transition: left 0.3s ease;
  }

  .logo-section {
    padding: 20px;
    margin-bottom: 20px;
  }

  .navigation {
    padding: 0 20px;
  }

  .pro-cta {
    margin: 0 20px 20px;
  }
}
</style>
