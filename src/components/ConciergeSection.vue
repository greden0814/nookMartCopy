<template>
  <section class="concierge-section">
    <div class="concierge-inner">
      <div class="concierge-content">
        <h2 class="concierge-title">Concierge Delivery Service</h2>
        <p class="concierge-desc">
          We're here to help. Yes, we're real people who love the game!
          If you're not convinced, shoot us a message. We'll get back to you in seconds.
        </p>

        <div class="features">
          <div class="feature-item">
            <div class="feature-icon">
              <el-icon><Clock /></el-icon>
            </div>
            <div>
              <h4 class="feature-title">24/7 Delivery</h4>
              <p class="feature-desc">Round-the-clock service, anytime you need it</p>
            </div>
          </div>
          <div class="feature-item">
            <div class="feature-icon support-icon">
              <el-icon><Headset /></el-icon>
            </div>
            <div>
              <h4 class="feature-title">Live Support</h4>
              <p class="feature-desc">Real people, real help, real fast</p>
            </div>
          </div>
        </div>

        <el-button type="primary" size="large" round class="cta-btn">
          Contact Support
          <el-icon><Message /></el-icon>
        </el-button>
      </div>

      <div class="concierge-visual">
        <div class="visual-card float-card-1">
          <span>💬</span>
          <span>Live Chat</span>
        </div>
        <div class="visual-card float-card-2">
          <span>🎮</span>
          <span>In-Game</span>
        </div>
        <div class="visual-card float-card-3">
          <span>📦</span>
          <span>Delivery</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Clock, Headset, Message } from '@element-plus/icons-vue'
</script>

<style scoped>
.concierge-section {
  padding: 100px 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.concierge-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}

.concierge-content {
  max-width: 520px;
}

.concierge-title {
  font-size: 40px;
  font-weight: 800;
  color: #1a1a2e;
  margin: 0 0 16px;
  line-height: 1.2;
}

.concierge-desc {
  font-size: 18px;
  line-height: 1.7;
  color: #666;
  margin: 0 0 40px;
}

.features {
  display: flex;
  flex-direction: column;
  gap: 24px;
  margin-bottom: 40px;
}

.feature-item {
  display: flex;
  gap: 16px;
  align-items: flex-start;
}

.feature-icon {
  width: 48px;
  height: 48px;
  min-width: 48px;
  background: rgba(67, 160, 71, 0.1);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  color: #43a047;
}

.support-icon {
  background: rgba(255, 179, 0, 0.1);
  color: #ffb300;
}

.feature-title {
  font-size: 18px;
  font-weight: 700;
  color: #1a1a2e;
  margin: 0 0 4px;
}

.feature-desc {
  font-size: 15px;
  color: #888;
  margin: 0;
}

.cta-btn {
  background: linear-gradient(135deg, #43a047, #66bb6a);
  border: none;
  font-size: 16px;
  font-weight: 600;
  padding: 16px 36px;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  box-shadow: 0 4px 20px rgba(67, 160, 71, 0.3);
  transition: all 0.3s;
}

.cta-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 28px rgba(67, 160, 71, 0.4);
}

.concierge-visual {
  position: relative;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.visual-card {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  padding: 24px 32px;
  background: white;
  border-radius: 20px;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.08);
  font-size: 14px;
  font-weight: 600;
  color: #333;
  border: 1px solid #f0f0f0;
  animation: floatCard 6s ease-in-out infinite;
}

.visual-card span:first-child {
  font-size: 40px;
}

.float-card-1 {
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.float-card-2 {
  top: 50%;
  right: 5%;
  animation-delay: 2s;
}

.float-card-3 {
  bottom: 10%;
  left: 20%;
  animation-delay: 4s;
}

@keyframes floatCard {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-16px); }
}

@media (max-width: 768px) {
  .concierge-inner {
    grid-template-columns: 1fr;
    gap: 48px;
  }

  .concierge-title {
    font-size: 30px;
  }

  .concierge-visual {
    height: 300px;
  }

  .visual-card {
    padding: 16px 24px;
  }

  .float-card-1 { left: 5%; }
  .float-card-2 { right: 0; }
  .float-card-3 { left: 10%; }
}
</style>
