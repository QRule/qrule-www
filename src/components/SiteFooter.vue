<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="footer-logo">
            <span class="logo-text">区融科技</span>
          </div>
          <p class="footer-desc">
            四川区融科技有限公司，致力于为企业提供领先的数字化转型解决方案与智能技术服务。
          </p>
        </div>

        <div class="footer-links">
          <h4>快速导航</h4>
          <ul>
            <li><router-link to="/">首页</router-link></li>
            <li><router-link to="/about">关于我们</router-link></li>
            <li><router-link to="/services">服务</router-link></li>
            <li><router-link to="/contact">联系我们</router-link></li>
          </ul>
        </div>

        <div class="footer-links">
          <h4>服务领域</h4>
          <ul>
            <li>数字化转型</li>
            <li>智能技术方案</li>
            <li>软件定制开发</li>
            <li>技术咨询</li>
          </ul>
        </div>

        <div class="footer-links">
          <h4>联系方式</h4>
          <ul>
            <li>四川省成都市</li>
            <li>contact@qrole.cn</li>
          </ul>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} 四川区融科技有限公司 版权所有</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--color-bg-dark);
  color: rgba(255, 255, 255, 0.75);
  padding: 80px 0 0;
}

.footer-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 48px;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
}

.logo-text {
  font-size: 18px;
  font-weight: 700;
  color: var(--color-text-inverse);
}

.footer-desc {
  font-size: 14px;
  line-height: 1.8;
}

.footer-links h4 {
  color: var(--color-text-inverse);
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 20px;
}

.footer-links ul {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.footer-links li,
.footer-links a {
  font-size: 14px;
  transition: color var(--transition);
}

.footer-links a:hover {
  color: var(--color-accent);
}

.footer-bottom {
  margin-top: 60px;
  padding: 24px 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  text-align: center;
  font-size: 13px;
}

@media (max-width: 768px) {
  .footer {
    padding: 48px 0 0;
  }

  .footer-grid {
    grid-template-columns: 1fr;
    gap: 36px;
  }

  .footer-bottom {
    margin-top: 36px;
  }
}
</style>
