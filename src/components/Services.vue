<script setup>
const services = [
  {
    icon: '🌐',
    title: '企业官网开发',
    description: '独立完成品牌官网全流程开发，从需求对接到上线运营。',
    features: ['响应式设计，适配 PC / 平板 / 手机', 'SEO 优化，提升搜索引擎排名', '内容管理系统，方便自主更新', '域名部署上线，一站式交付'],
    price: '1500 - 5000',
    unit: '元/站',
  },
  {
    icon: '🎬',
    title: '摄影摄像服务',
    description: '活动跟拍、产品拍摄、宣传片制作，从拍摄到后期全流程。',
    features: ['团建 / 户外活动全程跟拍', '产品 / 场景专业拍摄', '视频剪辑、调色、字幕包装'],
    price: '800 - 3000',
    unit: '元/场',
  },
  {
    icon: '📱',
    title: '小程序 / H5 开发',
    description: '轻量级应用开发，适合活动推广、品牌展示等场景。',
    features: ['Vue3 / Uni-app 跨端开发', '交互流畅，体验原生级', '对接微信生态', '快速交付，周期短'],
    price: '2000 - 8000',
    unit: '元/个',
  },
]
</script>

<template>
  <section id="services" class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          接单服务
        </h2>
        <p class="text-gray text-lg">价格透明，按需定制，欢迎咨询</p>
      </div>

      <!-- Service Cards -->
      <div class="grid md:grid-cols-3 gap-8 mb-16">
        <div
          v-for="service in services"
          :key="service.title"
          class="glow-card p-6 flex flex-col"
        >
          <div class="text-3xl mb-4">{{ service.icon }}</div>
          <h3 class="text-xl font-semibold text-white mb-2">{{ service.title }}</h3>
          <p class="text-gray text-sm mb-5 leading-relaxed">{{ service.description }}</p>

          <ul class="space-y-2 mb-6 flex-1">
            <li
              v-for="feature in service.features"
              :key="feature"
              class="flex items-start gap-2 text-sm text-gray-light"
            >
              <span class="text-primary mt-1 shrink-0">✓</span>
              <span>{{ feature }}</span>
            </li>
          </ul>

          <div class="border-t border-dark-border pt-4 mt-auto">
            <span class="text-2xl font-bold gradient-text">{{ service.price }}</span>
            <span class="text-gray text-sm ml-1">{{ service.unit }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
