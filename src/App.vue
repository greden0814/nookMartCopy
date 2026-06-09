<template>
  <div class="app">
    <NavHeader />
    <main>
      <HeroSection />
      <PopularProducts />
      <HowItWorks />
      <ConciergeSection />
    </main>
    <FooterSection />
  </div>
</template>

<script setup lang="ts">
import NavHeader from './components/NavHeader.vue'
import HeroSection from './components/HeroSection.vue'
import PopularProducts from './components/PopularProducts.vue'
import HowItWorks from './components/HowItWorks.vue'
import ConciergeSection from './components/ConciergeSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue',
    Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #fff;
  color: #333;
  line-height: 1.5;
}

.app {
  min-height: 100vh;
}

/* Override Element Plus primary color */
:root {
  --el-color-primary: #43a047;
  --el-color-primary-light-3: #66bb6a;
  --el-color-primary-light-5: #81c784;
  --el-color-primary-light-7: #a5d6a7;
  --el-color-primary-light-8: #c8e6c9;
  --el-color-primary-light-9: #e8f5e9;
  --el-color-primary-dark-2: #388e3c;
  --color-upperbg: lab(16.132% -.318035 -14.6672);
  --color-primary: #1a212b;
  --tw-outline-style: #2cc93e;
}
</style>
