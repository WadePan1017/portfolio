<script setup>
import screenshotFurniture from '../assets/project-furniture.png'
import screenshotZrzr from '../assets/project-zrzr.png'
import screenshotAi from '../assets/project-ai-tools.png'
import screenshotAdmin from '../assets/project-admin.png'
import screenshotPortfolio from '../assets/project-portfolio.png'
import casePhotography from '../assets/case-photography.png'
import caseRestaurant from '../assets/case-restaurant.png'
import caseEducation from '../assets/case-education.png'
import caseLaw from '../assets/case-law.png'
import caseRenovation from '../assets/case-renovation.png'

const cases = [
  {
    title: '上海非凡大师家居',
    category: '企业官网',
    description: '为家居企业独立交付的品牌展示网站，从需求对接到上线运营全程负责。',
    tags: ['企业站', '响应式', '上线运营'],
    highlights: [
      '产品分类展示、详情页、案例介绍等完整页面',
      '响应式适配 PC / 平板 / 手机',
      '集成在线咨询功能',
      '网站已正式上线运营',
    ],
    demo: 'http://www.topr8.cn/',
    screenshot: screenshotFurniture,
  },
  {
    title: 'ZRZR 正日移门官网',
    category: '企业官网',
    description: '为温州正日家居有限公司独立交付的品牌展示官网，定位"门的艺术家"高端品牌形象。',
    tags: ['Vue3', 'ScrollReveal', '企业站'],
    highlights: [
      '独立完成品牌视觉设计与前端开发',
      '产品分类展示、展厅浏览、发展历程等完整页面',
      'ScrollReveal 滚动动画增强交互体验',
      '网站已正式上线运营',
    ],
    demo: 'http://www.zrzr.top/',
    screenshot: screenshotZrzr,
  },
  {
    title: 'AI 工具导航站',
    category: '展示站',
    description: '为解决 AI 工具信息分散的问题，独立设计并开发的工具导航网站。',
    tags: ['Vue3', 'Tailwind CSS', 'Vite'],
    highlights: [
      '收录 50+ 工具，按 8 个分类组织',
      '组件化架构，数据与视图分离',
      '输入即搜索，支持名称和标签匹配',
      '响应式适配全设备',
    ],
    demo: 'https://WadePan1017.github.io/ai-tools-site/',
    screenshot: screenshotAi,
  },
  {
    title: 'Just Fulfillment 后台系统',
    category: '后台管理',
    description: '全栈后台管理系统，包含仪表盘数据可视化、文件管理、用户权限等企业级功能。',
    tags: ['Vue3', 'TypeScript', 'Node.js', 'Docker'],
    highlights: [
      'Vue3 + TypeScript 前端架构',
      'ECharts 数据可视化面板',
      '登录注册与路由鉴权',
      'Docker 容器化部署',
    ],
    demo: 'https://just-fulfillment-production-d6a9.up.railway.app/',
    screenshot: screenshotAdmin,
  },
  {
    title: 'Wade Studio 个人网站',
    category: '个人网站',
    description: '个人品牌展示站点，深色主题与极光紫配色建立视觉辨识度。',
    tags: ['Vue3', 'Tailwind CSS', '动画'],
    highlights: [
      '极光紫主题系统',
      '8 个独立组件，职责清晰',
      '打字机动画 + 锚点平滑滚动',
      '移动端完整适配',
    ],
    demo: 'https://WadePan1017.github.io/portfolio/',
    screenshot: screenshotPortfolio,
  },
  {
    title: '光影工作室官网',
    category: '摄影工作室',
    description: '摄影工作室模板案例，包含作品展示、套餐价格、预约咨询、客户评价。',
    tags: ['响应式', '图片画廊', '预约系统', '模板案例'],
    highlights: [
      '作品展示网格，hover 放大效果',
      '三档套餐价格对比',
      '在线预约表单',
      '客户评价模块',
    ],
    demo: 'cases/photography.html',
    screenshot: casePhotography,
  },
  {
    title: '味觉研究所官网',
    category: '餐饮品牌',
    description: '餐饮品牌模板案例，包含菜单展示、门店环境、预约订座、食客评价。',
    tags: ['响应式', '菜单展示', '预约系统', '模板案例'],
    highlights: [
      '招牌菜品展示 + 菜单价格',
      '门店环境图片画廊',
      '在线预约订座表单',
      '食客评价模块',
    ],
    demo: 'cases/restaurant.html',
    screenshot: caseRestaurant,
  },
  {
    title: '启航教育官网',
    category: '教育培训',
    description: '教育培训模板案例，包含课程体系、师资团队、学员成果、课程价格。',
    tags: ['响应式', '课程展示', '在线咨询', '模板案例'],
    highlights: [
      '四大课程方向展示',
      '师资团队 + 学员成果数据',
      '三档课程价格对比',
      '在线咨询预约表单',
    ],
    demo: 'cases/education.html',
    screenshot: caseEducation,
  },
  {
    title: '正衡律师事务所官网',
    category: '律师事务所',
    description: '律师事务所模板案例，包含服务领域、律师团队、典型案例、在线咨询。',
    tags: ['响应式', '团队展示', '案例展示', '模板案例'],
    highlights: [
      '六大服务领域展示',
      '律师团队 + 执业背景',
      '典型案例 + 处理结果',
      '在线咨询 + 隐私保护',
    ],
    demo: 'cases/law.html',
    screenshot: caseLaw,
  },
  {
    title: '栖木空间设计官网',
    category: '装修公司',
    description: '装修公司模板案例，包含装修案例、设计团队、材料工艺、免费报价。',
    tags: ['响应式', '案例画廊', '报价表单', '模板案例'],
    highlights: [
      '6套装修案例 + 风格/面积/预算',
      '设计师团队展示',
      '材料工艺 + 服务流程',
      '免费报价在线表单',
    ],
    demo: 'cases/renovation.html',
    screenshot: caseRenovation,
  },
]
</script>

<template>
  <section id="cases" class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          案例展示
        </h2>
        <p class="text-gray text-lg">已上线运营的项目与行业模板案例</p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="item in cases"
          :key="item.title"
          class="glow-card overflow-hidden group flex flex-col"
        >
          <!-- Screenshot -->
          <div class="h-48 relative overflow-hidden bg-dark-lighter">
            <img
              :src="item.screenshot"
              :alt="item.title + ' 截图'"
              loading="lazy"
              class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-dark-light/60 to-transparent"></div>
            <span class="absolute top-3 left-3 px-3 py-1 bg-primary/80 text-white text-xs rounded-full font-medium">
              {{ item.category }}
            </span>
          </div>

          <!-- Info -->
          <div class="p-5 flex flex-col flex-1">
            <h3 class="text-lg font-semibold text-white mb-2">{{ item.title }}</h3>
            <p class="text-gray text-sm mb-4 leading-relaxed">{{ item.description }}</p>

            <ul class="space-y-1.5 mb-4 flex-1">
              <li
                v-for="h in item.highlights"
                :key="h"
                class="flex items-start gap-2 text-xs text-gray-light"
              >
                <span class="text-primary mt-0.5 shrink-0">▸</span>
                <span>{{ h }}</span>
              </li>
            </ul>

            <div class="flex flex-wrap gap-2 mb-4">
              <span
                v-for="tag in item.tags"
                :key="tag"
                class="px-2.5 py-0.5 bg-primary/8 text-primary-light text-xs rounded-full border border-primary/10"
              >
                {{ tag }}
              </span>
            </div>

            <a
              :href="item.demo"
              target="_blank"
              rel="noopener noreferrer"
              class="block text-center py-2.5 bg-gradient-to-r from-primary/15 to-primary-light/15 hover:from-primary/25 hover:to-primary-light/25 text-primary-light rounded-lg text-sm font-medium transition-all border border-primary/10 hover:border-primary/30"
            >
              查看网站 →
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
