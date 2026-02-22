<script setup lang="ts">
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
            四川区融科技有限公司（QRole）成立于2020年，总部位于四川省成都市。
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
  max-width: 800px;
}

.intro-text p {
  font-size: 16px;
  line-height: 2;
  color: var(--color-text-light);
  margin-bottom: 16px;
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

@media (max-width: 768px) {
  .page-hero {
    padding: 120px 0 60px;
  }

  .page-hero-title {
    font-size: 36px;
  }

  .values-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
