<script setup lang="ts">
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  phone: '',
  company: '',
  message: '',
})

const isSubmitted = ref(false)

function handleSubmit() {
  isSubmitted.value = true
}

function resetForm() {
  form.name = ''
  form.email = ''
  form.phone = ''
  form.company = ''
  form.message = ''
  isSubmitted.value = false
}

const contactInfo = [
  {
    icon: '📍',
    title: '公司地址',
    content: '四川省成都市',
  },
  {
    icon: '📧',
    title: '电子邮箱',
    content: 'contact@qrule.cn',
  },
  {
    icon: '🕐',
    title: '工作时间',
    content: '周一至周五 9:00 - 18:00',
  },
]
</script>

<template>
  <section class="page-hero">
    <div class="container">
      <h1 class="page-hero-title">联系我们</h1>
      <p class="page-hero-subtitle">期待与您的合作，让我们共创价值</p>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <div class="contact-grid">
        <div class="contact-info">
          <h2 class="contact-heading">与我们取得联系</h2>
          <p class="contact-desc">
            无论您有任何技术需求或合作意向，我们的团队都随时准备为您服务。
            请填写表单或通过以下方式直接联系我们。
          </p>

          <div class="info-cards">
            <div v-for="info in contactInfo" :key="info.title" class="info-card">
              <span class="info-icon">{{ info.icon }}</span>
              <div>
                <h4 class="info-title">{{ info.title }}</h4>
                <p class="info-content">{{ info.content }}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="contact-form-wrapper">
          <div v-if="isSubmitted" class="form-success">
            <div class="success-icon">✓</div>
            <h3>提交成功</h3>
            <p>感谢您的留言，我们将尽快与您联系。</p>
            <button class="btn btn-primary" @click="resetForm">返回</button>
          </div>

          <form v-else class="contact-form" @submit.prevent="handleSubmit">
            <div class="form-row">
              <div class="form-group">
                <label for="name">姓名 *</label>
                <input
                  id="name"
                  v-model="form.name"
                  type="text"
                  placeholder="请输入您的姓名"
                  required
                />
              </div>
              <div class="form-group">
                <label for="email">邮箱 *</label>
                <input
                  id="email"
                  v-model="form.email"
                  type="email"
                  placeholder="请输入您的邮箱"
                  required
                />
              </div>
            </div>

            <div class="form-row">
              <div class="form-group">
                <label for="phone">电话</label>
                <input
                  id="phone"
                  v-model="form.phone"
                  type="tel"
                  placeholder="请输入您的电话"
                />
              </div>
              <div class="form-group">
                <label for="company">公司</label>
                <input
                  id="company"
                  v-model="form.company"
                  type="text"
                  placeholder="请输入公司名称"
                />
              </div>
            </div>

            <div class="form-group">
              <label for="message">留言 *</label>
              <textarea
                id="message"
                v-model="form.message"
                rows="5"
                placeholder="请描述您的需求或问题"
                required
              ></textarea>
            </div>

            <button type="submit" class="btn btn-primary btn-block">提交留言</button>
          </form>
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

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 64px;
  align-items: start;
}

.contact-heading {
  font-size: 32px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 16px;
}

.contact-desc {
  font-size: 16px;
  color: var(--color-text-light);
  line-height: 1.8;
  margin-bottom: 40px;
}

.info-cards {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.info-card {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 20px;
  background-color: var(--color-bg-alt);
  border-radius: 10px;
}

.info-icon {
  font-size: 28px;
}

.info-title {
  font-size: 14px;
  font-weight: 600;
  color: var(--color-primary);
  margin-bottom: 4px;
}

.info-content {
  font-size: 14px;
  color: var(--color-text-light);
}

/* Form */
.contact-form-wrapper {
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: 16px;
  padding: 40px;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  font-size: 14px;
  font-weight: 600;
  color: var(--color-primary);
  margin-bottom: 8px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 12px 16px;
  border: 1px solid var(--color-border);
  border-radius: 8px;
  font-size: 14px;
  font-family: var(--font-family);
  color: var(--color-text);
  transition: border-color var(--transition);
  outline: none;
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: var(--color-accent);
}

.form-group textarea {
  resize: vertical;
}

.btn-block {
  width: 100%;
  text-align: center;
}

/* Success State */
.form-success {
  text-align: center;
  padding: 40px 0;
}

.success-icon {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  background-color: #28a745;
  color: white;
  font-size: 28px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.form-success h3 {
  font-size: 24px;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 12px;
}

.form-success p {
  font-size: 16px;
  color: var(--color-text-light);
  margin-bottom: 28px;
}

@media (max-width: 768px) {
  .page-hero {
    padding: 120px 0 60px;
  }

  .page-hero-title {
    font-size: 36px;
  }

  .contact-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .contact-form-wrapper {
    padding: 24px;
  }

  .form-row {
    grid-template-columns: 1fr;
    gap: 0;
  }
}
</style>
