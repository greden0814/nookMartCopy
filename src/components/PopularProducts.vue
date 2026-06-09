<template>
  <section class="products-section">
    <div class="section-header">
      <h2 class="section-title">Popular Products</h2>
      <p class="section-desc">Most sought-after items by our community</p>
    </div>

    <div class="products-grid">
      <div
        v-for="product in products"
        :key="product.name"
        class="product-card"
        @mouseenter="product.hovered = true"
        @mouseleave="product.hovered = false"
      >
        <div class="card-image">
          <img :src="product.image" :alt="product.name" />
          <div class="card-overlay">
            <el-button size="small" round class="quick-view">Quick View</el-button>
          </div>
        </div>
        <div class="card-info">
          <span class="card-category">{{ product.category }}</span>
          <h3 class="card-name">{{ product.name }}</h3>
          <div class="card-footer">
            <span class="card-price">
              <span class="price-symbol">$</span>{{ product.price.toFixed(2) }}
            </span>
            <el-button :icon="ShoppingCart" circle size="small" class="add-cart" />
          </div>
        </div>
      </div>
    </div>

    <div class="view-all">
      <el-button round class="view-all-btn">
        View All Products
        <el-icon><ArrowRight /></el-icon>
      </el-button>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import { ShoppingCart, ArrowRight } from '@element-plus/icons-vue'

interface Product {
  name: string
  category: string
  price: number
  image: string
  hovered: boolean
}

const products = reactive<Product[]>([
  { name: 'Fish Bait', category: 'Item', price: 0.99, image: '', hovered: false },
  { name: '100 Nook Miles Tickets', category: 'NMT', price: 2.99, image: '', hovered: false },
  { name: 'Iron Nugget', category: 'Material', price: 0.49, image: '', hovered: false },
  { name: '4,200,000 Bells', category: 'Bells', price: 4.99, image: '', hovered: false },
  { name: 'Gold Nugget', category: 'Material', price: 1.99, image: '', hovered: false },
  { name: 'Wheat Field', category: 'Item', price: 0.99, image: '', hovered: false },
  { name: 'Plain Party-Lights Arch', category: 'Item', price: 1.49, image: '', hovered: false },
  { name: 'All Golden Tools', category: 'Set', price: 12.99, image: '', hovered: false },
])
</script>

<style scoped>
.products-section {
  max-width: 1200px;
  margin: 0 auto;
  padding: 100px 24px;
}

.section-header {
  text-align: center;
  margin-bottom: 56px;
}

.section-title {
  font-size: 40px;
  font-weight: 800;
  color: #1a1a2e;
  margin: 0 0 12px;
}

.section-desc {
  font-size: 18px;
  color: #888;
  margin: 0;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 24px;
}

.product-card {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.06);
  transition: all 0.3s;
  cursor: pointer;
  border: 1px solid #f0f0f0;
}

.product-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.1);
  border-color: #e0e0e0;
}

.card-image {
  height: 200px;
  background: linear-gradient(135deg, #e8f5e9, #f1f8e9);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.card-image img {
  width: 80px;
  height: 80px;
  object-fit: contain;
  opacity: 0.15;
  font-size: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s;
}

.product-card:hover .card-overlay {
  opacity: 1;
}

.quick-view {
  background: white;
  border: none;
  font-weight: 600;
  color: #333;
}

.card-info {
  padding: 16px 20px 20px;
}

.card-category {
  font-size: 12px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #43a047;
}

.card-name {
  font-size: 16px;
  font-weight: 700;
  color: #1a1a2e;
  margin: 6px 0 16px;
  line-height: 1.3;
}

.card-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-price {
  font-size: 22px;
  font-weight: 800;
  color: #1a1a2e;
}

.price-symbol {
  font-size: 14px;
  font-weight: 600;
  vertical-align: super;
}

.add-cart {
  background: #f0faf0;
  border: none;
  color: #43a047;
  font-size: 16px;
  transition: all 0.3s;
}

.add-cart:hover {
  background: #43a047;
  color: white;
}

.view-all {
  text-align: center;
  margin-top: 48px;
}

.view-all-btn {
  padding: 14px 36px;
  font-size: 16px;
  font-weight: 600;
  border: 2px solid #43a047;
  color: #43a047;
  transition: all 0.3s;
}

.view-all-btn:hover {
  background: #43a047;
  color: white;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 30px;
  }

  .products-grid {
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 16px;
  }

  .card-image {
    height: 150px;
  }
}
</style>
