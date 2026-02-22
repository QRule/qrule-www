<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navLinks = [
  { name: '首页', path: '/' },
  { name: '关于我们', path: '/about' },
  { name: '服务', path: '/services' },
  { name: '联系我们', path: '/contact' },
]

function handleScroll() {
  isScrolled.value = window.scrollY > 20
}

function toggleMobileMenu() {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

function closeMobileMenu() {
  isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header class="header" :class="{ scrolled: isScrolled }">
    <div class="container header-inner">
      <router-link to="/" class="logo" @click="closeMobileMenu">
        <span class="logo-text">区融科技</span>
      </router-link>

      <nav class="nav-desktop">
        <router-link
          v-for="link in navLinks"
          :key="link.path"
          :to="link.path"
          class="nav-link"
          :class="{ active: route.path === link.path }"
        >
          {{ link.name }}
        </router-link>
      </nav>

      <button
        class="hamburger"
        :class="{ open: isMobileMenuOpen }"
        @click="toggleMobileMenu"
        aria-label="Toggle menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <Transition name="slide">
        <nav v-if="isMobileMenuOpen" class="nav-mobile">
          <router-link
            v-for="link in navLinks"
            :key="link.path"
            :to="link.path"
            class="nav-link"
            :class="{ active: route.path === link.path }"
            @click="closeMobileMenu"
          >
            {{ link.name }}
          </router-link>
        </nav>
      </Transition>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  height: var(--header-height);
  transition: all var(--transition);
  background-color: transparent;
}

.header.scrolled {
  background-color: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.08);
}

.header-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100%;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-weight: 700;
  z-index: 1001;
}

.logo-text {
  font-size: 20px;
  color: var(--color-text-inverse);
  transition: color var(--transition);
}

.scrolled .logo-text {
  color: var(--color-primary);
}

.nav-desktop {
  display: flex;
  gap: 8px;
}

.nav-desktop .nav-link {
  padding: 8px 20px;
  border-radius: 6px;
  font-size: 15px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.85);
  transition: all var(--transition);
}

.scrolled .nav-desktop .nav-link {
  color: var(--color-text);
}

.nav-desktop .nav-link:hover,
.nav-desktop .nav-link.active {
  color: var(--color-accent);
}

.scrolled .nav-desktop .nav-link:hover,
.scrolled .nav-desktop .nav-link.active {
  color: var(--color-accent);
  background-color: rgba(233, 69, 96, 0.08);
}

.hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 32px;
  height: 32px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1001;
  padding: 0;
}

.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background-color: var(--color-text-inverse);
  transition: all var(--transition);
  border-radius: 1px;
}

.scrolled .hamburger span {
  background-color: var(--color-primary);
}

.hamburger.open span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.open span:nth-child(2) {
  opacity: 0;
}

.hamburger.open span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

.nav-mobile {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: var(--color-primary);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.nav-mobile .nav-link {
  font-size: 22px;
  font-weight: 600;
  color: var(--color-text-inverse);
  padding: 12px 24px;
  border-radius: 8px;
  transition: all var(--transition);
}

.nav-mobile .nav-link.active,
.nav-mobile .nav-link:hover {
  color: var(--color-accent);
}

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
  opacity: 0;
}

@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }

  .hamburger {
    display: flex;
  }
}
</style>
