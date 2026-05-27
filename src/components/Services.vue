<script setup>
const capabilities = [
  {
    icon: '🌐',
    title: '企业官网 / 品牌站',
    description: '从需求分析到上线运营，独立交付完整品牌展示网站。',
    features: ['响应式设计，适配全设备', 'SEO 优化，提升搜索排名', 'ScrollReveal 动画增强体验', '已上线运营 2 个商业客户'],
  },
  {
    icon: '📊',
    title: '后台管理系统',
    description: '全栈开发管理后台，数据可视化与业务逻辑一体化。',
    features: ['Vue3 + TypeScript 前端架构', 'Element Plus + ECharts 可视化', 'Node.js + SQLite 后端', 'Docker 容器化部署'],
  },
  {
    icon: '🎬',
    title: '摄影摄像 & 后期',
    description: '活动跟拍、产品拍摄、视频剪辑，从素材到成片全流程。',
    features: ['团建 / 户外活动全程跟拍', 'Premiere Pro 剪辑调色', 'After Effects 动态特效', '2 年摄影行业经验'],
  },
]

const pricing = [
  {
    icon: '🌐',
    service: '官网 / 品牌站',
    price: '1,800 - 3,500',
    unit: '元',
    cycle: '3-5 天',
    includes: ['响应式设计', 'SEO 基础优化', '部署上线', '1 个月免费维护'],
  },
  {
    icon: '🤖',
    service: 'AI 工具站',
    price: '3,000 - 6,000',
    unit: '元',
    cycle: '5-7 天',
    includes: ['前端界面开发', 'API 接入集成', '部署上线', '1 个月免费维护'],
  },
  {
    icon: '📊',
    service: '后台管理系统',
    price: '4,000 - 8,000',
    unit: '元',
    cycle: '7-10 天',
    includes: ['数据可视化面板', '用户权限管理', '部署上线', '1 个月免费维护'],
  },
  {
    icon: '📄',
    service: '落地页 / 单页',
    price: '800 - 1,500',
    unit: '元',
    cycle: '1-2 天',
    includes: ['高转化设计', '动效交互', '部署上线', '基础维护'],
  },
  {
    icon: '🧩',
    service: 'Chrome 插件',
    price: '2,000 - 4,000',
    unit: '元',
    cycle: '3-5 天',
    includes: ['功能开发', 'Chrome 商店上架', '文档说明', '1 个月免费维护'],
  },
]

const process = [
  { step: '01', title: '需求沟通', desc: '了解项目目标、功能需求和设计偏好' },
  { step: '02', title: '方案报价', desc: '提供详细方案和透明报价，确认后签约' },
  { step: '03', title: '设计开发', desc: '按节点推进，每周同步进度' },
  { step: '04', title: '验收交付', desc: '源码 + 部署文档 + 使用说明，满意后付尾款' },
]
</script>

<template>
  <!-- 能力范围 -->
  <section id="services" class="py-24 px-6 bg-dark-light/30">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          接单服务
        </h2>
        <p class="text-gray text-lg">专注 AI 辅助开发，高效交付高质量项目</p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="item in capabilities"
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

  <!-- 价格表 -->
  <section class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          服务报价
        </h2>
        <p class="text-gray text-lg">透明定价，拒绝隐性费用</p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="item in pricing"
          :key="item.service"
          class="glow-card p-6 flex flex-col"
        >
          <div class="flex items-center gap-3 mb-4">
            <span class="text-2xl">{{ item.icon }}</span>
            <h3 class="text-lg font-semibold text-white">{{ item.service }}</h3>
          </div>

          <div class="mb-4">
            <span class="text-3xl font-bold gradient-text">{{ item.price }}</span>
            <span class="text-gray text-sm ml-1">{{ item.unit }}</span>
          </div>

          <div class="flex items-center gap-2 mb-5 text-sm text-gray">
            <span>&#9202;</span>
            <span>交付周期 {{ item.cycle }}</span>
          </div>

          <ul class="space-y-2 flex-1">
            <li
              v-for="inc in item.includes"
              :key="inc"
              class="flex items-start gap-2 text-sm text-gray-light"
            >
              <span class="text-primary mt-1 shrink-0">&#10003;</span>
              <span>{{ inc }}</span>
            </li>
          </ul>
        </div>
      </div>

      <p class="text-center text-gray text-sm mt-8">
        * 具体价格根据项目需求和复杂度确定，欢迎咨询获取精准报价
      </p>
    </div>
  </section>

  <!-- 合作流程 -->
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
          付款方式：50% 定金 + 50% 验收后付清 &nbsp;|&nbsp; 交付内容：源码 + 部署文档 + 使用说明 + 1 个月维护
        </p>
      </div>
    </div>
  </section>
</template>
