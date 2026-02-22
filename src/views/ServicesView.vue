<script setup lang="ts">
const services = [
  {
    icon: '☁️',
    title: '云计算服务',
    desc: '提供公有云、私有云及混合云架构设计与实施，帮助企业实现IT基础设施的现代化升级。',
    features: ['云架构规划', '云迁移服务', '运维管理', '成本优化'],
  },
  {
    icon: '📊',
    title: '大数据解决方案',
    desc: '构建企业级数据中台，实现数据采集、存储、分析到可视化的全链路能力。',
    features: ['数据中台建设', '数据分析', '可视化大屏', '数据治理'],
  },
  {
    icon: '🤖',
    title: '人工智能应用',
    desc: '基于先进的AI算法，为企业打造智能化业务流程与决策支持系统。',
    features: ['智能客服', '图像识别', '自然语言处理', '预测分析'],
  },
  {
    icon: '📱',
    title: '软件定制开发',
    desc: '根据客户业务需求，提供从需求分析到交付运维的全流程软件开发服务。',
    features: ['Web 应用开发', '移动端开发', '微服务架构', 'API 开发'],
  },
  {
    icon: '🔗',
    title: '物联网平台',
    desc: '打造万物互联的智能生态，实现设备管理、数据采集与业务融合。',
    features: ['设备接入管理', '边缘计算', '实时监控', '场景联动'],
  },
  {
    icon: '🛡️',
    title: '技术咨询',
    desc: '由资深技术专家团队为企业提供全方位的技术评估与数字化战略规划。',
    features: ['技术架构评估', '数字化规划', '技术选型', '团队培训'],
  },
]
</script>

<template>
  <section class="page-hero">
    <div class="container">
      <h1 class="page-hero-title">服务</h1>
      <p class="page-hero-subtitle">全方位的技术解决方案，助力企业数字化转型</p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <div class="services-grid">
        <div v-for="(service, index) in services" :key="index" class="service-card">
          <div class="service-icon">{{ service.icon }}</div>
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-desc">{{ service.desc }}</p>
          <ul class="service-features">
            <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <section class="process-section section">
    <div class="container">
      <h2 class="section-title">服务流程</h2>
      <p class="section-subtitle">标准化流程，确保项目高质量交付</p>
      <div class="process-grid">
        <div class="process-step">
          <div class="step-number">01</div>
          <h4 class="step-title">需求沟通</h4>
          <p class="step-desc">深入了解客户业务场景与核心需求</p>
        </div>
        <div class="process-arrow">→</div>
        <div class="process-step">
          <div class="step-number">02</div>
          <h4 class="step-title">方案设计</h4>
          <p class="step-desc">制定详细的技术方案与实施计划</p>
        </div>
        <div class="process-arrow">→</div>
        <div class="process-step">
          <div class="step-number">03</div>
          <h4 class="step-title">开发实施</h4>
          <p class="step-desc">敏捷开发，持续交付可用产品</p>
        </div>
        <div class="process-arrow">→</div>
        <div class="process-step">
          <div class="step-number">04</div>
          <h4 class="step-title">交付运维</h4>
          <p class="step-desc">系统上线及持续运维保障支持</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.page-hero {
  background: linear-gradient(135deg, #1a1a2e 0%, #0f3460 100%);
  padding: 160px 0 80px;
  text-align: center;
}

.page-hero-title {
  font-size: 48px;
  font-weight: 800;
  color: var(--color-text-inverse);
  margin-bottom: 16px;
}

.page-hero-subtitle {
  font-size: 18px;
  color: rgba(255, 255, 255, 0.7);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.service-card {
  padding: 40px 32px;
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: 12px;
  transition: all var(--transition);
}

.service-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
  border-color: var(--color-accent);
}

.service-icon {
  font-size: 44px;
  margin-bottom: 20px;
}

.service-title {
  font-size: 22px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 12px;
}

.service-desc {
  font-size: 14px;
  color: var(--color-text-light);
  line-height: 1.8;
  margin-bottom: 20px;
}

.service-features {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.service-features li {
  font-size: 13px;
  padding: 4px 14px;
  background-color: var(--color-bg-alt);
  border-radius: 20px;
  color: var(--color-text-light);
}

/* Process */
.process-section {
  background-color: var(--color-bg-alt);
}

.process-grid {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  gap: 16px;
}

.process-step {
  flex: 1;
  max-width: 220px;
  text-align: center;
}

.step-number {
  font-size: 40px;
  font-weight: 800;
  color: var(--color-accent);
  margin-bottom: 12px;
}

.step-title {
  font-size: 18px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 8px;
}

.step-desc {
  font-size: 14px;
  color: var(--color-text-light);
  line-height: 1.6;
}

.process-arrow {
  color: var(--color-accent);
  font-size: 24px;
  margin-top: 20px;
  font-weight: 700;
}

@media (max-width: 1024px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .page-hero {
    padding: 120px 0 60px;
  }

  .page-hero-title {
    font-size: 36px;
  }

  .services-grid {
    grid-template-columns: 1fr;
  }

  .process-grid {
    flex-direction: column;
    align-items: center;
  }

  .process-arrow {
    transform: rotate(90deg);
    margin: 0;
  }
}
</style>
