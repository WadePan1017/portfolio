<script setup>
const services = [
  {
    icon: '🌐',
    title: '企业官网 / 品牌站',
    description: '从需求分析到上线运营，独立交付完整品牌展示网站。',
    features: ['响应式设计，适配全设备', 'SEO 优化，提升搜索排名', '动效交互增强体验', '已上线运营多个商业客户'],
  },
  {
    icon: '🖼️',
    title: '展示站 / 作品集',
    description: '个人IP、工作室、摄影师专属展示网站，突出视觉效果。',
    features: ['视觉优先设计', '图片/视频画廊', '响应式适配', '快速上线'],
  },
  {
    icon: '📊',
    title: '后台管理系统',
    description: '全栈开发管理后台，数据可视化与业务逻辑一体化。',
    features: ['Vue3 + TypeScript 前端', '数据可视化面板', '用户权限管理', 'Docker 部署'],
  },
]

const process = [
  { step: '01', title: '需求沟通', desc: '了解项目目标、功能需求和设计偏好' },
  { step: '02', title: '方案报价', desc: '提供详细方案和透明报价，确认后签约' },
  { step: '03', title: '设计开发', desc: '按节点推进，每周同步进度' },
  { step: '04', title: '验收交付', desc: '源码 + 部署文档 + 使用说明，满意后付尾款' },
]

const reasons = [
  { icon: '✅', text: '已上线多个真实项目' },
  { icon: '✅', text: '支持源码交付' },
  { icon: '✅', text: '支持后续维护' },
  { icon: '✅', text: 'AI 辅助开发，提高交付效率' },
  { icon: '✅', text: '需求确认后快速开发' },
]
</script>

<template>
  <!-- Services -->
  <section id="services" class="py-24 px-6 bg-dark-light/30">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          服务范围
        </h2>
        <p class="text-gray text-lg">专注网站开发，高效交付高质量项目</p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="item in services"
          :key="item.title"
          class="glow-card p-6 flex flex-col"
        >
          <div class="text-3xl mb-4">{{ item.icon }}</div>
          <h3 class="text-xl font-semibold text-white mb-2">{{ item.title }}</h3>
          <p class="text-gray text-sm mb-5 leading-relaxed">{{ item.description }}</p>

          <ul class="space-y-2 flex-1">
            <li
              v-for="feature in item.features"
              :key="feature"
              class="flex items-start gap-2 text-sm text-gray-light"
            >
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>{{ feature }}</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- Trust -->
  <section class="py-20 px-6">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          为什么选择 Wade Studio
        </h2>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
        <div
          v-for="r in reasons"
          :key="r.text"
          class="glow-card p-5 flex items-center gap-3"
        >
          <span class="text-xl shrink-0">{{ r.icon }}</span>
          <span class="text-gray-light text-sm">{{ r.text }}</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing -->
  <section id="pricing" class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          服务报价
        </h2>
        <p class="text-gray text-lg">透明定价，拒绝隐性费用</p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Tier 1 -->
        <div class="glow-card p-6 flex flex-col">
          <div class="flex items-center gap-3 mb-4">
            <span class="text-2xl">📦</span>
            <h3 class="text-lg font-semibold text-white">模板安装版</h3>
          </div>
          <div class="mb-4">
            <span class="text-3xl font-bold gradient-text">199</span>
            <span class="text-gray text-sm ml-1">元起</span>
          </div>
          <div class="flex items-center gap-2 mb-5 text-sm text-gray">
            <span>&#9202;</span>
            <span>交付周期 1-2 天</span>
          </div>
          <ul class="space-y-2 flex-1">
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>套用精选模板</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>替换 Logo / 图片 / 文字</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>响应式适配</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>部署上线指导</span>
            </li>
          </ul>
          <p class="text-gray text-xs mt-4 pt-4 border-t border-dark-border">
            适合已有模板快速搭建，仅替换文字、图片、Logo。<br>
            不含定制设计，不含后台开发。
          </p>
          <a
            href="#contact"
            class="mt-6 block text-center py-2.5 border border-dark-border hover:border-primary/40 text-gray hover:text-white rounded-lg text-sm font-medium transition-all hover:bg-dark-lighter"
          >
            立即咨询
          </a>
        </div>

        <!-- Tier 2 -->
        <div class="glow-card p-6 flex flex-col relative overflow-hidden">
          <div class="absolute top-0 right-0 px-3 py-1 bg-primary text-white text-xs font-medium rounded-bl-lg">
            推荐
          </div>
          <div class="flex items-center gap-3 mb-4">
            <span class="text-2xl">🌐</span>
            <h3 class="text-lg font-semibold text-white">标准企业官网</h3>
          </div>
          <div class="mb-4">
            <span class="text-3xl font-bold gradient-text">599-999</span>
            <span class="text-gray text-sm ml-1">元</span>
          </div>
          <div class="flex items-center gap-2 mb-5 text-sm text-gray">
            <span>&#9202;</span>
            <span>交付周期 3-5 天</span>
          </div>
          <ul class="space-y-2 flex-1">
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>多页面定制设计</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>响应式全设备适配</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>联系表单 / 在线咨询</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>SEO 基础优化</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>部署上线 + 1个月维护</span>
            </li>
          </ul>
          <a
            href="#contact"
            class="mt-6 block text-center py-2.5 bg-gradient-to-r from-primary to-primary-light hover:from-primary-light hover:to-accent text-white rounded-lg text-sm font-medium transition-all shadow-lg shadow-primary/25"
          >
            立即咨询
          </a>
        </div>

        <!-- Tier 3 -->
        <div class="glow-card p-6 flex flex-col">
          <div class="flex items-center gap-3 mb-4">
            <span class="text-2xl">⚙️</span>
            <h3 class="text-lg font-semibold text-white">定制开发</h3>
          </div>
          <div class="mb-4">
            <span class="text-3xl font-bold gradient-text">1500+</span>
            <span class="text-gray text-sm ml-1">元</span>
          </div>
          <div class="flex items-center gap-2 mb-5 text-sm text-gray">
            <span>&#9202;</span>
            <span>交付周期 5-10 天</span>
          </div>
          <ul class="space-y-2 flex-1">
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>全新视觉设计</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>定制功能开发</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>后台管理系统</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>SEO + 性能优化</span>
            </li>
            <li class="flex items-start gap-2 text-sm text-gray-light">
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>源码交付 + 3个月维护</span>
            </li>
          </ul>
          <a
            href="#contact"
            class="mt-6 block text-center py-2.5 border border-dark-border hover:border-primary/40 text-gray hover:text-white rounded-lg text-sm font-medium transition-all hover:bg-dark-lighter"
          >
            立即咨询
          </a>
        </div>
      </div>

      <p class="text-center text-gray text-sm mt-8">
        * 具体价格根据项目需求和复杂度确定，欢迎咨询获取精准报价
      </p>
    </div>
  </section>

  <!-- Process -->
  <section class="py-24 px-6 bg-dark-light/30">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          合作流程
        </h2>
        <p class="text-gray text-lg">从需求到交付，全程透明高效</p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="item in process"
          :key="item.step"
          class="glow-card p-6 text-center"
        >
          <div class="text-4xl font-bold gradient-text mb-3">{{ item.step }}</div>
          <h3 class="text-lg font-semibold text-white mb-2">{{ item.title }}</h3>
          <p class="text-gray text-sm">{{ item.desc }}</p>
        </div>
      </div>

      <div class="text-center mt-12">
        <p class="text-gray text-sm">
          付款方式：50% 定金 + 50% 验收后付清 &nbsp;|&nbsp; 交付内容：源码 + 部署文档 + 使用说明
        </p>
      </div>
    </div>
  </section>
</template>
