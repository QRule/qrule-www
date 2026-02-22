<script setup lang="ts">
import { ref, onMounted } from 'vue'

const isVisible = ref(false)

const features = [
  {
    icon: '🔧',
    title: '技术驱动',
    desc: '以前沿技术为核心，打造高效可靠的数字化解决方案',
  },
  {
    icon: '🎯',
    title: '精准定制',
    desc: '深入理解客户需求，提供量身定制的技术服务',
  },
  {
    icon: '🚀',
    title: '快速交付',
    desc: '敏捷开发流程，确保项目高质量按时交付',
  },
  {
    icon: '🛡️',
    title: '安全可靠',
    desc: '严格的安全标准与质量管控，保障系统稳定运行',
  },
]

onMounted(() => {
  isVisible.value = true
})
</script>

<template>
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="container hero-content" :class="{ visible: isVisible }">
      <h1 class="hero-title">
        以科技之力<br />
        <span class="highlight">驱动数字未来</span>
      </h1>
      <p class="hero-subtitle">
        四川区融科技有限公司 — 专注于企业数字化转型与智能技术解决方案
      </p>
      <div class="hero-actions">
        <router-link to="/services" class="btn btn-primary">探索服务</router-link>
        <router-link to="/about" class="btn btn-outline">了解更多</router-link>
      </div>
    </div>
  </section>

  <section class="section features-section">
    <div class="container">
      <h2 class="section-title">为什么选择我们</h2>
      <p class="section-subtitle">以专业技术能力，为企业创造切实价值</p>
      <div class="features-grid">
        <div v-for="(feature, index) in features" :key="index" class="feature-card">
          <div class="feature-icon">{{ feature.icon }}</div>
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-desc">{{ feature.desc }}</p>
        </div>
      </div>
    </div>
  </section>

  <section class="section cta-section">
    <div class="container cta-content">
      <h2 class="cta-title">准备好开启数字化转型了吗？</h2>
      <p class="cta-desc">让我们携手共创智能未来</p>
      <router-link to="/contact" class="btn btn-primary">联系我们</router-link>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
  z-index: 0;
}

.hero-bg::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at 70% 30%, rgba(233, 69, 96, 0.15) 0%, transparent 50%),
    radial-gradient(circle at 30% 70%, rgba(15, 52, 96, 0.3) 0%, transparent 50%);
}

.hero-content {
  position: relative;
  z-index: 1;
  padding-top: var(--header-height);
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}

.hero-content.visible {
  opacity: 1;
  transform: translateY(0);
}

.hero-title {
  font-size: 56px;
  font-weight: 800;
  color: var(--color-text-inverse);
  line-height: 1.2;
  margin-bottom: 24px;
}

.highlight {
  background: linear-gradient(135deg, var(--color-accent), var(--color-accent-light));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 20px;
  color: rgba(255, 255, 255, 0.7);
  margin-bottom: 48px;
  max-width: 560px;
}

.hero-actions {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

/* Features */
.features-section {
  background-color: var(--color-bg);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
}

.feature-card {
  padding: 40px 28px;
  border-radius: 12px;
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  text-align: center;
  transition: all var(--transition);
}

.feature-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
  border-color: var(--color-accent);
}

.feature-icon {
  font-size: 40px;
  margin-bottom: 20px;
}

.feature-title {
  font-size: 20px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 12px;
}

.feature-desc {
  font-size: 14px;
  color: var(--color-text-light);
  line-height: 1.8;
}

/* CTA */
.cta-section {
  background-color: var(--color-bg-alt);
}

.cta-content {
  text-align: center;
}

.cta-title {
  font-size: 36px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 16px;
}

.cta-desc {
  font-size: 18px;
  color: var(--color-text-light);
  margin-bottom: 40px;
}

@media (max-width: 1024px) {
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 36px;
  }

  .hero-subtitle {
    font-size: 16px;
  }

  .features-grid {
    grid-template-columns: 1fr;
  }

  .cta-title {
    font-size: 28px;
  }
}
</style>
