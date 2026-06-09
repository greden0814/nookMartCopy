<template>
  <section class="how-section">
    <div class="section-header">
      <h2 class="section-title">How Nookmart Works</h2>
      <p class="section-desc">
        The best way to buy Nook Miles Tickets or Bells in Animal Crossing.
        We truly offer it all!
      </p>
    </div>

    <div class="steps-container">
      <div v-for="(step, index) in steps" :key="step.title" class="step-card">
        <div class="step-number">{{ index + 1 }}</div>
        <div class="step-icon-wrapper">
          <el-icon class="step-icon"><component :is="step.icon" /></el-icon>
        </div>
        <h3 class="step-title">{{ step.title }}</h3>
        <p class="step-desc">{{ step.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Promotion, ShoppingCartFull, SuccessFilled } from '@element-plus/icons-vue'

const steps = [
  {
    icon: Promotion,
    title: 'Open Your Island Gates',
    description:
      'Head to your airport and open your gates for visitors. Share your Dodo Code with us and we\'ll be right there.',
  },
  {
    icon: ShoppingCartFull,
    title: 'Place Your Order',
    description:
      'Choose from a large catalogue of items and sets. Each delivery may require multiple trips from your assigned delivery staff.',
  },
  {
    icon: SuccessFilled,
    title: 'We Deliver Your Order',
    description:
      'Sit back and relax! Our team delivers straight to your island in minutes. Enjoy your new items!',
  },
]
</script>

<style scoped>
.how-section {
  padding: 100px 24px;
  background: linear-gradient(135deg, #f8fdf5 0%, #e8f5e9 100%);
}

.section-header {
  text-align: center;
  margin-bottom: 64px;
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
}

.section-title {
  font-size: 40px;
  font-weight: 800;
  color: #1a1a2e;
  margin: 0 0 12px;
}

.section-desc {
  font-size: 18px;
  color: #666;
  margin: 0;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
}

.steps-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
  max-width: 1000px;
  margin: 0 auto;
}

.step-card {
  text-align: center;
  padding: 40px 28px;
  background: white;
  border-radius: 20px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.06);
  position: relative;
  transition: all 0.3s;
  border: 1px solid #f0f0f0;
}

.step-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.1);
}

.step-number {
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  width: 28px;
  height: 28px;
  background: linear-gradient(135deg, #43a047, #66bb6a);
  color: white;
  border-radius: 50%;
  font-size: 14px;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: center;
}

.step-icon-wrapper {
  width: 64px;
  height: 64px;
  background: rgba(67, 160, 71, 0.1);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
}

.step-icon {
  font-size: 28px;
  color: #43a047;
}

.step-title {
  font-size: 20px;
  font-weight: 700;
  color: #1a1a2e;
  margin: 0 0 12px;
}

.step-desc {
  font-size: 15px;
  line-height: 1.7;
  color: #666;
  margin: 0;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 30px;
  }

  .steps-container {
    grid-template-columns: 1fr;
    gap: 24px;
  }
}
</style>
