<script setup>
import screenshotAi from '../assets/project-ai-tools.png'
import screenshotPortfolio from '../assets/project-portfolio.png'
import screenshotFurniture from '../assets/project-furniture.png'
import screenshotAdmin from '../assets/project-admin.png'
import screenshotZrzr from '../assets/project-zrzr.png'

const projects = [
  {
    title: 'AI 工具导航站',
    description: '为解决 AI 工具信息分散、难以查找的问题，独立设计并开发了一款工具导航网站。',
    tags: ['Vue3', 'Tailwind CSS', 'Vite', 'Pinia'],
    highlights: [
      '收录 50+ 工具，按 8 个分类组织（聊天、图像、视频、编程等）',
      '采用组件化架构：ToolCard / SearchBar / CategoryTabs 独立封装，数据与视图分离',
      '实现输入即搜索，支持工具名称和标签双重匹配',
      '响应式适配 320px-1920px 全设备，Tailwind 断点覆盖',
      '部署至 GitHub Pages，访问量稳定增长',
    ],
    demo: 'https://WadePan1017.github.io/ai-tools-site/',
    github: 'https://github.com/WadePan1017/ai-tools-site',
    screenshot: screenshotAi,
  },
  {
    title: '个人作品集网站',
    description: '为求职打造的个人展示站点，通过深色主题与极光紫配色建立视觉辨识度。',
    tags: ['Vue3', 'Tailwind CSS', '响应式', '动画'],
    highlights: [
      '设计极光紫主题系统：渐变光晕、发光卡片边框、自定义滚动条',
      '拆分为 8 个独立组件（Hero / Timeline / About / Skills 等），职责清晰',
      '实现 Hero 区打字机动画 + 锚点平滑滚动交互',
      '完成移动端适配，导航折叠、触控交互正常',
    ],
    demo: 'https://WadePan1017.github.io/portfolio/',
    github: 'https://github.com/WadePan1017/portfolio',
    screenshot: screenshotPortfolio,
  },
  {
    title: '上海非凡大师家居',
    description: '为家居企业独立交付的品牌展示网站，从需求对接到上线运营全程负责。',
    tags: ['企业站', '响应式', '上线运营'],
    highlights: [
      '与客户沟通需求，独立完成页面设计与前端开发',
      '实现产品分类展示、详情页、案例介绍等完整页面',
      '响应式适配 PC / 平板 / 手机，确保多端体验一致',
      '集成在线咨询功能，网站已正式上线运营',
    ],
    demo: 'http://www.topr8.cn/',
    github: 'https://github.com/WadePan1017',
    screenshot: screenshotFurniture,
  },
  {
    title: 'Just Fulfillment 后台管理系统',
    description: '全栈后台管理系统，包含仪表盘数据可视化、文件管理、用户权限等企业级功能模块。',
    tags: ['Vue3', 'TypeScript', 'Element Plus', 'ECharts', 'Node.js', 'SQLite'],
    highlights: [
      '采用 Vue3 + TypeScript 前端架构，Element Plus 组件库构建管理界面',
      '集成 ECharts 实现仪表盘数据可视化，直观展示业务指标',
      '实现文件下载管理、笔记管理、待办事项等核心业务模块',
      'Node.js + SQLite 后端，Docker 容器化部署至 Railway 平台',
      '完整的登录注册与路由鉴权，保障系统安全性',
    ],
    demo: 'https://just-fulfillment-production-d6a9.up.railway.app/',
    github: 'https://github.com/WadePan1017/Public',
    screenshot: screenshotAdmin,
  },
  {
    title: 'ZRZR 正日移门官网',
    description: '为温州正日家居有限公司独立交付的品牌展示官网，从需求对接到上线全程负责。',
    tags: ['Vue3', 'Vite', 'ScrollReveal', '响应式', '企业站'],
    highlights: [
      '独立完成品牌视觉设计与前端开发，定位"门的艺术家"高端品牌形象',
      '实现产品分类展示、展厅浏览、发展历程等完整页面体系',
      '采用 ScrollReveal 滚动动画增强页面交互体验',
      '响应式适配 PC / 平板 / 手机，确保多端体验一致',
      '网站已正式上线运营，服务客户日常业务推广',
    ],
    demo: 'http://www.zrzr.top/',
    github: 'https://github.com/WadePan1017',
    screenshot: screenshotZrzr,
  },
]
</script>

<template>
  <section id="projects" class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          项目展示
        </h2>
        <p class="text-gray text-lg">我独立开发的部分项目</p>
      </div>

      <div class="flex flex-wrap justify-center gap-8">
        <div
          v-for="project in projects"
          :key="project.title"
          class="glow-card overflow-hidden group w-full md:w-[calc(50%-1rem)] lg:w-[calc(33.333%-1.333rem)]"
        >
          <!-- Project Screenshot -->
          <div class="h-48 relative overflow-hidden bg-dark-lighter">
            <img
              :src="project.screenshot"
              :alt="project.title + ' 截图'"
              loading="lazy"
              class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-dark-light/60 to-transparent"></div>
          </div>

          <!-- Project Info -->
          <div class="p-6 relative z-10">
            <h3 class="text-xl font-semibold text-white mb-3">{{ project.title }}</h3>
            <p class="text-gray text-sm mb-4 leading-relaxed">{{ project.description }}</p>

            <!-- Highlights -->
            <ul class="space-y-2 mb-5">
              <li
                v-for="highlight in project.highlights"
                :key="highlight"
                class="flex items-start gap-2 text-sm text-gray-light"
              >
                <span class="text-primary mt-1 shrink-0">▸</span>
                <span>{{ highlight }}</span>
              </li>
            </ul>

            <!-- Tags -->
            <div class="flex flex-wrap gap-2 mb-5">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="px-3 py-1 bg-primary/8 text-primary-light text-xs rounded-full border border-primary/10"
              >
                {{ tag }}
              </span>
            </div>

            <!-- Links -->
            <div class="flex gap-3">
              <a
                :href="project.demo"
                class="flex-1 text-center py-2.5 bg-gradient-to-r from-primary/15 to-primary-light/15 hover:from-primary/25 hover:to-primary-light/25 text-primary-light rounded-lg text-sm font-medium transition-all border border-primary/10 hover:border-primary/30"
              >
                在线演示
              </a>
              <a
                :href="project.github"
                class="flex-1 text-center py-2.5 border border-dark-border hover:border-primary/40 text-gray hover:text-white rounded-lg text-sm font-medium transition-all hover:bg-dark-lighter"
              >
                源码
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
