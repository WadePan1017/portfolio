<script setup>
const projects = [
  {
    title: 'AI 工具导航站',
    description: '收录 50 余个优质 AI 工具，支持分类筛选和实时搜索。涵盖聊天对话、图像生成、视频生成、编程开发等 8 个分类。',
    tags: ['Vue3', 'Tailwind CSS', 'Vite', 'Pinia'],
    highlights: [
      '组件化架构：ToolCard、SearchBar、CategoryTabs 独立封装',
      '数据驱动：工具数据与展示逻辑分离，便于扩展维护',
      '实时搜索：输入即过滤，支持名称和分类匹配',
      '响应式适配：Tailwind 断点覆盖全设备尺寸',
    ],
    demo: 'https://WadePan1017.github.io/ai-tools-site/',
    github: 'https://github.com/WadePan1017/ai-tools-site',
    gradient: 'from-violet-500 to-purple-600',
  },
  {
    title: '个人作品集网站',
    description: '深色主题响应式设计，展示个人信息、技能栈和项目经历。极光紫配色，视觉层次分明。',
    tags: ['Vue3', 'Tailwind CSS', '响应式', '动画'],
    highlights: [
      '极光紫主题：渐变光晕 + 卡片发光边框设计',
      '组件化开发：7 个独立组件，职责清晰',
      '打字机效果：Hero 区动态标题展示',
      '平滑滚动：锚点导航 + 平滑滚动交互',
    ],
    demo: 'https://WadePan1017.github.io/portfolio/',
    github: 'https://github.com/WadePan1017/portfolio',
    gradient: 'from-cyan-500 to-blue-600',
  },
  {
    title: '上海非凡大师家居',
    description: '为家居公司开发的品牌展示网站，包含产品展示、案例介绍和在线咨询功能。已上线运营。',
    tags: ['企业站', '响应式', '上线运营'],
    highlights: [
      '真实业务：为实际企业开发，已上线运营使用',
      '产品展示：商品分类、详情展示完整流程',
      '响应式设计：适配 PC、平板、手机多端',
      '在线咨询：集成客服咨询功能',
    ],
    demo: 'http://www.topr8.cn/',
    github: 'https://github.com/WadePan1017',
    gradient: 'from-emerald-500 to-teal-600',
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
        <p class="text-gray text-lg">我开发的部分项目</p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="project in projects"
          :key="project.title"
          class="glow-card overflow-hidden group"
        >
          <!-- Project Header -->
          <div :class="['h-48 bg-gradient-to-br', project.gradient, 'flex items-center justify-center relative overflow-hidden']">
            <div class="absolute inset-0 bg-black/10 group-hover:bg-black/0 transition-colors"></div>
            <svg class="w-16 h-16 text-white/20 group-hover:text-white/30 transition-colors" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
            </svg>
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
