<script setup>
const events = [
  {
    year: '2023',
    title: '开启前端之路',
    description: '自学 HTML、CSS、JavaScript，完成多个练手项目，奠定前端基础。',
    icon: '🚀',
  },
  {
    year: '2024',
    title: '掌握 Vue 框架',
    description: '深入学习 Vue 3 生态，独立开发 AI 工具导航站，收录 50+ 优质工具。',
    icon: '⚡',
  },
  {
    year: '2025',
    title: '首个商业项目上线',
    description: '为上海非凡大师家居开发品牌展示网站，正式上线运营，获得客户认可。',
    icon: '🏆',
  },
  {
    year: '2025',
    title: '作品集 & 持续精进',
    description: '打造个人作品集，持续探索前端工程化与视觉设计的融合。',
    icon: '✨',
  },
]
</script>

<template>
  <section id="timeline" class="py-24 px-6">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          成长经历
        </h2>
        <p class="text-gray text-lg">我的学习与实践之路</p>
      </div>

      <div class="relative">
        <!-- Center line -->
        <div class="absolute left-6 md:left-1/2 md:-translate-x-px top-0 bottom-0 w-0.5 bg-gradient-to-b from-primary via-accent to-primary/20"></div>

        <div class="space-y-12">
          <div
            v-for="(event, index) in events"
            :key="index"
            :class="[
              'relative flex items-start gap-6',
              index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse',
            ]"
          >
            <!-- Dot -->
            <div class="absolute left-6 md:left-1/2 -translate-x-1/2 w-12 h-12 rounded-full bg-dark-light border-2 border-primary flex items-center justify-center text-lg z-10 shadow-lg shadow-primary/20">
              {{ event.icon }}
            </div>

            <!-- Card -->
            <div :class="[
              'ml-16 md:ml-0 md:w-[calc(50%-2.5rem)]',
              index % 2 === 0 ? 'md:pr-0' : 'md:pl-0',
            ]">
              <div class="glow-card p-5">
                <span class="text-sm font-semibold text-primary-light tracking-wider">{{ event.year }}</span>
                <h3 class="text-lg font-semibold text-white mt-1 mb-2">{{ event.title }}</h3>
                <p class="text-gray text-sm leading-relaxed">{{ event.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
