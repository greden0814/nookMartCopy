<template>
  <header class="nav-header">
    <div class="header-upper">
      <img src="../assets/present.webp" class="present-icon" />
      <span class="present-text">US${{ giftsPrice }} AWAY FROM 5 MYSTERY GIFTS</span>
      <img src="../assets/present.webp" class="present-icon" />
    </div>
    <div class="header-inner">
      <div class="logo" @click="scrollToTop">
        <button type="button" class="drawer" @click="mobileMenuOpen = !mobileMenuOpen">
          <span class="sr-only">Open menu</span>
          <svg xmlns="http://www.w3.org/2000/svg" class="drawerIcon" aria-hidden="true" fill="none" viewBox="0 0 24 24"
            stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
        <img draggable="false" alt="Nookmart Logo" width="204" height="100" decoding="async" data-nimg="1"
          class="h-14 pl-3" style="color:transparent; margin-left: 20px;" src="../assets/logo.svg">
      </div>

      <nav class="nav-links">
        <!-- <a href="#" class="nav-link">Browse Store</a> -->
        <!-- <a href="#" class="nav-link">How It Works</a> -->
        <a href="#" class="nav-link">FAQ</a>
        <a href="#" class="nav-link">News</a>
        <a href="#" class="nav-link">
          <svg xmlns="http://www.w3.org/2000/svg" class="clubIcon" fill="none" viewBox="0 0 1664 1472" stroke-width="2"
            stroke="currentColor">
            <path fill="currentColor"
              d="M1472 1216H192q-24 0-44 38.5t-20 89.5t20 89.5t44 38.5h1280q24 0 44-38.5t20-89.5t-20-89.5t-44-38.5zM128 128q-53 0-90.5 37.5T0 256t37.5 90.5T128 384l80 703h1248l80-703q53 0 90.5-37.5T1664 256t-37.5-90.5T1536 128t-90.5 37.5T1408 256q0 56 41 94q-153 183-207 236.5t-90 53.5q-34 0-83-66.5T899 301q28-17 44.5-46t16.5-63q0-53-37.5-90.5T832 64t-90.5 37.5T704 192q0 34 16.5 63t44.5 46Q644 507 595 573.5T512 640q-36 0-90-53.5T215 350q41-38 41-94q0-53-37.5-90.5T128 128z">
            </path>
          </svg>
          Club</a>
      </nav>
      <div class="search-group">
        <el-input v-model="searchText" size="large" class="custom-input" placeholder="Search..." clearable />
      </div>

      <div class="currency-group">
        <el-dropdown trigger="click">
          <!-- <el-button class="currency-btn" circle size="small"> -->
          <el-button class="currency-text">
            <span style="margin-right:12px;">{{ curCur }}</span>
            <el-icon>
              <ArrowDown />
            </el-icon>
          </el-button>
          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item v-for="(label, code) in currencyList" :key="code">
                {{ label }}
              </el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>
      </div>
      <div class="header-actions">
        <el-dropdown trigger="click" split-button class="new-horizons">
          <!-- <el-button class="currency-text2" type="success"> -->
          New Horizons
          <!-- </el-button> -->
          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item v-for="(label, code) in currencyList" :key="code">
                {{ label }}
              </el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>

        <el-badge :value="3" class="cart-badge">
          <a class="group relative flex items-center justify-center p-2" href="/cart">
            <svg xmlns="http://www.w3.org/2000/svg"
              class="shopping-icon text-primary-text group-hover:text-primary-text/80" aria-hidden="true"
              viewBox="0 0 20 20" fill="currentColor">
              <path
                d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z">
              </path>
            </svg>
          </a>
        </el-badge>
        <button class="mobile-menu-btn" @click="mobileMenuOpen = !mobileMenuOpen">
          <span></span><span></span><span></span>
        </button>
      </div>
    </div>

    <Transition name="mobile-menu">
      <div v-if="mobileMenuOpen" class="mobile-menu">
        <a href="#" class="mobile-link">Browse Store</a>
        <a href="#" class="mobile-link">How It Works</a>
        <a href="#" class="mobile-link">FAQ</a>
        <a href="#" class="mobile-link">News</a>
        <a href="#" class="mobile-link">Club</a>
        <el-button type="primary" round class="mobile-sign-in">
          Sign In <el-icon>
            <ArrowRight />
          </el-icon>
        </el-button>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'
import { ShoppingCart, ArrowRight, ArrowDown } from '@element-plus/icons-vue'

const mobileMenuOpen = ref(false)
let giftsPrice = ref('10.00')
let searchText = ref('')
let currencyList = ref({
  USD: '$ USD',
  EUR: '€ EUR',
  GBP: '£ GBP',
  CAD: 'C$ CAD',
  AUD: 'A$ AUD',
  JPY: '¥ JPY'
})
let curCur = ref('')
onMounted(() => {
  // Simulate fetching gifts price from API
  curCur.value = currencyList.value.USD
})

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<style scoped lang="scss">
.nav-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(0, 0, 0, 0.06);

  .header-upper {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    background: var(--color-upperbg);
    color: var(--el-color-primary);
    font-size: 14px;
    padding: 4px 0;

    .present-text {
      font-weight: 500;
      color: #fff;
    }

    .present-icon {
      width: 16px;
      height: 16px;
    }
  }
}

.header-inner {
  margin: 0 auto;
  padding: 0 24px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: var(--color-primary);

  .drawer {
    color: #fff;
    background-color: var(--color-primary);
    border: none;

    .sr-only {
      clip-path: inset(50%);
      white-space: nowrap;
      border-width: 0;
      width: 1px;
      height: 1px;
      margin: -1px;
      padding: 0;
      position: absolute;
      overflow: hidden;
    }

    .drawerIcon {
      width: 3vmin;
      // height: 24px;
    }
  }
}

.logo {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  user-select: none;
}

.logo-leaf {
  font-size: 28px;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 32px;
  margin-left: 24px;
}

.nav-link {
  text-decoration: none;
  color: #fff;
  font-size: 15px;
  font-weight: 400;
  transition: color 0.2s;
  position: relative;

  .clubIcon {
    width: 16px;
    height: 16px;
    margin-right: 4px;
  }
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--el-color-primary);
  transition: width 0.2s;
}

.nav-link:hover {
  color: var(--el-color-primary);
}

.nav-link:hover::after {
  width: 100%;
}

.search-group {
  margin-left: 24px;
  margin-right: 24px;
  flex: 1;
}

.custom-input :deep(.el-input__wrapper) {
  box-shadow: 0 0 0 1px #d9d9d9 inset;
  transition: box-shadow 0.2s ease;
  border-radius: .375rem;
  padding: 8px 12px;
}

.custom-input :deep(.el-input__wrapper.is-focus) {
  box-shadow: 0 0 0 2px var(--el-color-primary) inset;
}

.custom-input :deep(.el-input__inner) {
  caret-color: var(--el-color-primary);
  height: 20px !important;
}


// .focus-visible\:outline-offset-0:focus-visible {
//   outline-offset: 0px;
// }

// .focus-visible\:outline-2:focus-visible {
//   outline-style: var(--tw-outline-style);
//   outline-width: 2px;
// }

// .focus-visible\:outline-secondary:focus-visible {
//   outline-color: var(--color-secondary);
// }

.currency-group {
  width: 100px;
  padding: 0 3px;
  margin-right: 24px;

  :deep(.el-dropdown) {
    color: #fff;
  }

  :deep(.currency-text) {
    color: #fff;
    width: 90px;
    box-sizing: border-box;
    background: var(--color-primary);
    border-color: #fff;
    border-radius: .375rem;
  }

  :deep(.currency-text[aria-expanded="true"]) {
    border-color: var(--tw-outline-style);
    border-width: 2px;
  }

  :deep(.ad) {
    margin-left: 12px;
  }
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 12px;

  :deep(.new-horizons .el-button-group button) {
    background: linear-gradient(135deg, var(--el-color-primary), #66bb6a);
    border: none;
    font-weight: 600;
    color: #fff;
  }
}

.cart-badge :deep(.el-badge__content) {
  background: var(--el-color-primary);
}

.cart-badge :deep(.shopping-icon) {
  width: 32px;
  height: 32px;
  fill: #eee;
}

.cart-btn {
  border: none;
  background: #f0faf0;
  color: var(--el-color-primary);
  font-size: 18px;
}

.sign-in-btn {
  background: linear-gradient(135deg, var(--el-color-primary), #66bb6a);
  border: none;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 4px;
}

.arrow-icon {
  margin-left: 2px;
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  line-height: 0;

}

.mobile-menu-btn svg {
  width: 24px;
  height: 24px;
}

.mobile-menu {
  display: none;
  padding: 16px 24px 24px;
  background: white;
  border-top: 1px solid #eee;
}

.mobile-link {
  display: block;
  padding: 12px 0;
  text-decoration: none;
  color: #333;
  font-size: 16px;
  font-weight: 500;
  border-bottom: 1px solid #f5f5f5;
}

.mobile-sign-in {
  margin-top: 16px;
  width: 100%;
  background: linear-gradient(135deg, var(--el-color-primary), #66bb6a);
  border: none;
}

.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: all 0.3s ease;
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }

  .sign-in-btn {
    display: none;
  }

  .mobile-menu-btn {
    display: flex;
  }

  .mobile-menu {
    display: block;
  }
}
</style>
