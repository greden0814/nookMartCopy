<template>
  <section class="hero-section">
    <div class="hero-bg">
      <div class="floating-leaf leaf-1">🍃</div>
      <div class="floating-leaf leaf-2">🌿</div>
      <div class="floating-leaf leaf-3">🍂</div>
      <div class="floating-leaf leaf-4">🌱</div>
    </div>
    <div class="hero-content">
      <div class="hero-badge">
        <span class="badge-dot"></span>
        Animal Crossing
      </div>
      <h1 class="hero-title">
        We Deliver Items.<br />
        <span class="highlight">In 5 Minutes.</span>
      </h1>
      <p class="hero-subtitle">
        The fastest and most trusted Animal Crossing New Horizons item delivery service.
        Buy Bells, Nook Miles Tickets, Villagers, furniture, and more!
      </p>
      <div class="hero-actions">
        <el-button type="primary" size="large" round class="browse-btn">
          Browse Store
          <el-icon class="btn-icon"><ArrowRight /></el-icon>
        </el-button>
        <el-button size="large" round class="how-btn">
          How It Works
          <el-icon class="btn-icon"><ArrowDown /></el-icon>
        </el-button>
      </div>
      <div class="hero-stats">
        <div class="stat-item">
          <span class="stat-number">9,464+</span>
          <span class="stat-label">Reviews</span>
        </div>
        <div class="stat-divider"></div>
        <div class="stat-item">
          <span class="stat-number">5 min</span>
          <span class="stat-label">Delivery</span>
        </div>
        <div class="stat-divider"></div>
        <div class="stat-item">
          <span class="stat-number">24/7</span>
          <span class="stat-label">Support</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ArrowRight, ArrowDown } from '@element-plus/icons-vue'
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #f8fdf5 0%, #e8f5e9 30%, #f1f8e9 60%, #fff8e1 100%);
  padding: 120px 24px 80px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.floating-leaf {
  position: absolute;
  font-size: 32px;
  opacity: 0.4;
  animation: float 6s ease-in-out infinite;
}

.leaf-1 { top: 15%; left: 8%; animation-delay: 0s; }
.leaf-2 { top: 25%; right: 12%; animation-delay: 1.5s; font-size: 24px; }
.leaf-3 { bottom: 20%; left: 15%; animation-delay: 3s; font-size: 28px; }
.leaf-4 { bottom: 30%; right: 8%; animation-delay: 4.5s; }

@keyframes float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(5deg); }
}

.hero-content {
  text-align: center;
  max-width: 720px;
  position: relative;
  z-index: 1;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 20px;
  background: rgba(67, 160, 71, 0.1);
  border: 1px solid rgba(67, 160, 71, 0.2);
  border-radius: 100px;
  font-size: 14px;
  font-weight: 600;
  color: #43a047;
  margin-bottom: 24px;
}

.badge-dot {
  width: 6px;
  height: 6px;
  background: #43a047;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.hero-title {
  font-size: 56px;
  font-weight: 800;
  line-height: 1.15;
  color: #1a1a2e;
  margin: 0 0 20px;
}

.highlight {
  background: linear-gradient(135deg, #43a047, #81c784, #ffb300);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 18px;
  line-height: 1.6;
  color: #666;
  margin: 0 0 36px;
  max-width: 560px;
  margin-left: auto;
  margin-right: auto;
}

.hero-actions {
  display: flex;
  gap: 16px;
  justify-content: center;
  margin-bottom: 48px;
  flex-wrap: wrap;
}

.browse-btn {
  background: linear-gradient(135deg, #43a047, #66bb6a);
  border: none;
  font-size: 16px;
  font-weight: 600;
  padding: 16px 36px;
  box-shadow: 0 4px 20px rgba(67, 160, 71, 0.3);
  transition: all 0.3s;
}

.browse-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 28px rgba(67, 160, 71, 0.4);
}

.how-btn {
  background: white;
  border: 2px solid #e0e0e0;
  font-size: 16px;
  font-weight: 600;
  padding: 16px 36px;
  color: #333;
  transition: all 0.3s;
}

.how-btn:hover {
  border-color: #43a047;
  color: #43a047;
  transform: translateY(-2px);
}

.btn-icon {
  margin-left: 6px;
}

.hero-stats {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 32px;
}

.stat-item {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.stat-number {
  font-size: 24px;
  font-weight: 800;
  color: #1a1a2e;
}

.stat-label {
  font-size: 14px;
  color: #888;
  font-weight: 500;
}

.stat-divider {
  width: 1px;
  height: 40px;
  background: #ddd;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 36px;
  }

  .hero-subtitle {
    font-size: 16px;
  }

  .hero-stats {
    gap: 20px;
  }

  .stat-number {
    font-size: 20px;
  }
}
</style>
