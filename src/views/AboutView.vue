<script setup lang="ts">
const milestones = [
  { year: '2020', event: '公司成立，扎根成都' },
  { year: '2021', event: '核心技术团队组建完成，首批客户签约' },
  { year: '2022', event: '完成多个大型数字化转型项目' },
  { year: '2023', event: '业务拓展至西南多省，团队规模突破50人' },
  { year: '2024', event: '发布自主研发智能化平台产品' },
  { year: '2025', event: '持续创新，服务客户突破100家' },
]

const values = [
  {
    title: '创新',
    desc: '持续探索前沿技术，以创新思维解决复杂问题',
  },
  {
    title: '务实',
    desc: '脚踏实地做技术，以交付结果为导向',
  },
  {
    title: '协作',
    desc: '与客户紧密合作，共同推进项目目标的实现',
  },
  {
    title: '卓越',
    desc: '追求技术卓越，不断提升服务品质与标准',
  },
]
</script>

<template>
  <section class="page-hero">
    <div class="container">
      <h1 class="page-hero-title">关于我们</h1>
      <p class="page-hero-subtitle">了解区融科技的故事与愿景</p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <div class="about-intro">
        <div class="intro-text">
          <h2 class="section-title" style="text-align: left">公司简介</h2>
          <p>
            四川区融科技有限公司（QRule）成立于2020年，总部位于四川省成都市。
            我们是一家专注于企业数字化转型与智能技术解决方案的科技公司。
          </p>
          <p>
            公司拥有一支经验丰富的技术团队，核心成员来自国内知名互联网企业，
            在云计算、大数据、人工智能、物联网等领域拥有深厚的技术积累。
          </p>
          <p>
            我们致力于用技术赋能企业，帮助客户在数字经济时代实现业务升级与价值增长。
          </p>
        </div>
        <div class="intro-visual">
          <div class="visual-card">
            <div class="visual-logo">Q</div>
            <div class="visual-name">QRule</div>
            <div class="visual-slogan">科技驱动 · 智领未来</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section" style="background-color: var(--color-bg-alt)">
    <div class="container">
      <h2 class="section-title">核心价值观</h2>
      <p class="section-subtitle">指引我们前行的力量</p>
      <div class="values-grid">
        <div v-for="(value, index) in values" :key="index" class="value-card">
          <div class="value-index">{{ String(index + 1).padStart(2, '0') }}</div>
          <h3 class="value-title">{{ value.title }}</h3>
          <p class="value-desc">{{ value.desc }}</p>
        </div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <h2 class="section-title">发展历程</h2>
      <p class="section-subtitle">一路走来的每一步</p>
      <div class="timeline">
        <div
          v-for="(milestone, index) in milestones"
          :key="index"
          class="timeline-item"
          :class="{ reverse: index % 2 !== 0 }"
        >
          <div class="timeline-content">
            <span class="timeline-year">{{ milestone.year }}</span>
            <p class="timeline-event">{{ milestone.event }}</p>
          </div>
          <div class="timeline-dot"></div>
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

.about-intro {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: center;
}

.intro-text p {
  font-size: 16px;
  line-height: 2;
  color: var(--color-text-light);
  margin-bottom: 16px;
}

.intro-visual {
  display: flex;
  justify-content: center;
}

.visual-card {
  width: 300px;
  height: 300px;
  border-radius: 20px;
  background: linear-gradient(135deg, #1a1a2e 0%, #0f3460 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.visual-logo {
  font-size: 72px;
  font-weight: 900;
  color: var(--color-accent);
}

.visual-name {
  font-size: 28px;
  font-weight: 700;
  color: var(--color-text-inverse);
  letter-spacing: 4px;
}

.visual-slogan {
  font-size: 13px;
  color: rgba(255, 255, 255, 0.6);
  letter-spacing: 2px;
}

/* Values */
.values-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
}

.value-card {
  padding: 36px 24px;
  background: var(--color-bg);
  border-radius: 12px;
  border: 1px solid var(--color-border);
  transition: all var(--transition);
}

.value-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 32px rgba(0, 0, 0, 0.06);
}

.value-index {
  font-size: 36px;
  font-weight: 800;
  color: rgba(233, 69, 96, 0.15);
  margin-bottom: 16px;
}

.value-title {
  font-size: 20px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 12px;
}

.value-desc {
  font-size: 14px;
  color: var(--color-text-light);
  line-height: 1.8;
}

/* Timeline */
.timeline {
  position: relative;
  max-width: 700px;
  margin: 0 auto;
  padding: 20px 0;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 2px;
  background-color: var(--color-border);
  transform: translateX(-50%);
}

.timeline-item {
  display: flex;
  align-items: center;
  margin-bottom: 40px;
  position: relative;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

.timeline-content {
  width: calc(50% - 30px);
  text-align: right;
  padding-right: 12px;
}

.timeline-item.reverse .timeline-content {
  order: 2;
  text-align: left;
  padding-right: 0;
  padding-left: 12px;
  margin-left: auto;
}

.timeline-dot {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background-color: var(--color-accent);
  border: 3px solid var(--color-bg);
  box-shadow: 0 0 0 2px var(--color-accent);
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1;
}

.timeline-year {
  font-size: 20px;
  font-weight: 800;
  color: var(--color-accent);
}

.timeline-event {
  font-size: 14px;
  color: var(--color-text-light);
  margin-top: 4px;
}

@media (max-width: 768px) {
  .page-hero {
    padding: 120px 0 60px;
  }

  .page-hero-title {
    font-size: 36px;
  }

  .about-intro {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .values-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .timeline::before {
    left: 20px;
  }

  .timeline-item {
    flex-direction: row;
  }

  .timeline-content {
    width: auto;
    text-align: left;
    padding-left: 48px;
    padding-right: 0;
  }

  .timeline-item.reverse .timeline-content {
    order: unset;
    padding-left: 48px;
    margin-left: 0;
  }

  .timeline-dot {
    left: 20px;
  }
}
</style>
