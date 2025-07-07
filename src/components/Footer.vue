<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="copyright">
        <span class="copyright-text"
          >© 2022 Horizon UI. All Rights Reserved. Made with love by
        </span>
        <span class="copyright-brand">Simmmple!</span>
      </div>
      <div class="footer-links">
        <a href="#" class="footer-link">Marketplace</a>
        <a href="#" class="footer-link">License</a>
        <a href="#" class="footer-link">Terms of Use</a>
        <a href="#" class="footer-link">Blog</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  padding: 30px;
  background: var(--secondary-grey-300);
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1528px;
  margin: 0 auto;
}

.copyright {
  display: flex;
  align-items: center;
}

.copyright-text {
  font-size: 14px;
  font-weight: 400;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-600);
}

.copyright-brand {
  font-size: 14px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-600);
}

.footer-links {
  display: flex;
  gap: 40px;
  align-items: center;
}

.footer-link {
  font-size: 14px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: -0.28px;
  color: var(--secondary-grey-600);
  text-decoration: none;
  text-align: center;
  transition: color 0.2s ease;
}

.footer-link:hover {
  color: var(--secondary-grey-900);
}

@media (max-width: 768px) {
  .footer {
    padding: 20px 15px;
  }

  .footer-content {
    flex-direction: column;
    gap: 20px;
    text-align: center;
  }

  .footer-links {
    gap: 20px;
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
