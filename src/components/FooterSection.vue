<template>
  <footer class="main-footer">
    <div class="footer-inner">
      <div class="footer-brand">
        <div class="footer-logo">
          <span class="logo-leaf">🍃</span>
          <span class="logo-text">Nookmart</span>
        </div>
        <p class="footer-brand-desc">
          The fastest and most trusted Animal Crossing New Horizons item delivery service.
          Buy Bells, Nook Miles Tickets, Villagers, furniture, items, and more!
        </p>
        <div class="social-links">
          <a href="#" class="social-link" title="Discord"><el-icon><ChatDotRound /></el-icon></a>
          <a href="#" class="social-link" title="Twitter"><el-icon><Share /></el-icon></a>
          <a href="#" class="social-link" title="Instagram"><el-icon><Camera /></el-icon></a>
          <a href="#" class="social-link" title="Trustpilot"><el-icon><Star /></el-icon></a>
        </div>
      </div>

      <div class="footer-links">
        <div class="link-group">
          <h4 class="link-group-title">Shop</h4>
          <a href="#" class="footer-link">Browse Store</a>
          <a href="#" class="footer-link">Popular Items</a>
          <a href="#" class="footer-link">Featured Items</a>
          <a href="#" class="footer-link">Collections</a>
          <a href="#" class="footer-link">Nook Miles Tickets</a>
        </div>
        <div class="link-group">
          <h4 class="link-group-title">Support</h4>
          <a href="#" class="footer-link">How It Works</a>
          <a href="#" class="footer-link">FAQ</a>
          <a href="#" class="footer-link">Contact Us</a>
          <a href="#" class="footer-link">Delivery Status</a>
        </div>
        <div class="link-group">
          <h4 class="link-group-title">Company</h4>
          <a href="#" class="footer-link">About Us</a>
          <a href="#" class="footer-link">News</a>
          <a href="#" class="footer-link">Bellionaire Club</a>
          <a href="#" class="footer-link">Careers</a>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <div class="footer-bottom-inner">
        <span>&copy; 2026 Nookmart. All rights reserved.</span>
        <div class="legal-links">
          <a href="#">Privacy Policy</a>
          <a href="#">Terms of Service</a>
          <a href="#">Cookie Policy</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { ChatDotRound, Share, Camera, Star } from '@element-plus/icons-vue'
</script>

<style scoped>
.main-footer {
  background: #1a1a2e;
  color: #ccc;
}

.footer-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 24px;
  display: grid;
  grid-template-columns: 1.5fr 2fr;
  gap: 80px;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
}

.footer-logo .logo-leaf {
  font-size: 28px;
}

.footer-logo .logo-text {
  font-size: 22px;
  font-weight: 800;
  background: linear-gradient(135deg, #81c784, #a5d6a7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.footer-brand-desc {
  font-size: 15px;
  line-height: 1.7;
  color: #999;
  margin: 0 0 24px;
  max-width: 360px;
}

.social-links {
  display: flex;
  gap: 12px;
}

.social-link {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.06);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999;
  font-size: 18px;
  transition: all 0.3s;
  text-decoration: none;
}

.social-link:hover {
  background: #43a047;
  color: white;
  transform: translateY(-2px);
}

.footer-links {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.link-group-title {
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: white;
  margin: 0 0 20px;
}

.footer-link {
  display: block;
  font-size: 15px;
  color: #999;
  text-decoration: none;
  padding: 6px 0;
  transition: color 0.2s;
}

.footer-link:hover {
  color: #81c784;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.footer-bottom-inner {
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 14px;
  color: #666;
}

.legal-links {
  display: flex;
  gap: 24px;
}

.legal-links a {
  color: #666;
  text-decoration: none;
  transition: color 0.2s;
}

.legal-links a:hover {
  color: #81c784;
}

@media (max-width: 768px) {
  .footer-inner {
    grid-template-columns: 1fr;
    gap: 48px;
    padding: 60px 24px;
  }

  .footer-links {
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
  }

  .footer-bottom-inner {
    flex-direction: column;
    gap: 12px;
    text-align: center;
  }

  .legal-links {
    gap: 16px;
  }
}
</style>
