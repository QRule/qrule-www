<script setup lang="ts">
import NavHeader from './components/NavHeader.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <NavHeader />
  <main class="main-content">
    <router-view />
  </main>
  <SiteFooter />
</template>

<style scoped>
.main-content {
  flex: 1;
}
</style>
