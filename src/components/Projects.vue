<script setup>
const projects = [
  {
    title: 'AI 工具导航站',
    description: '一个聚合 AI 工具的导航网站，支持搜索、分类筛选、深色模式。使用 Vue3 + TailwindCSS 构建，组件化开发，响应式布局。',
    tags: ['Vue3', 'Tailwind CSS', 'Vite', '组件化'],
    demo: '#',
    github: '#',
    gradient: 'from-indigo-500 to-purple-600',
  },
  {
    title: '个人作品集网站',
    description: '你正在浏览的这个网站！用于展示我的项目和技能，支持响应式布局和平滑滚动动画。',
    tags: ['Vue3', 'Tailwind CSS', '响应式', '动画'],
    demo: '#',
    github: '#',
    gradient: 'from-cyan-500 to-blue-600',
  },
  {
    title: '待办事项应用',
    description: '一个简洁的待办事项管理应用，支持添加、删除、标记完成状态，数据本地持久化存储。',
    tags: ['Vue3', 'LocalStorage', 'CSS3'],
    demo: '#',
    github: '#',
    gradient: 'from-emerald-500 to-teal-600',
  },
]
</script>

<template>
  <section id="projects" class="py-20 px-6">
    <div class="max-w-6xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold text-white text-center mb-4">
        项目展示
      </h2>
      <p class="text-gray text-center mb-12">我开发的部分项目</p>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="project in projects"
          :key="project.title"
          class="group bg-dark-light border border-dark-lighter rounded-2xl overflow-hidden hover:border-primary/30 transition-all hover:-translate-y-1"
        >
          <!-- Project Header -->
          <div :class="['h-48 bg-gradient-to-br', project.gradient, 'flex items-center justify-center']">
            <svg class="w-16 h-16 text-white/30" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
            </svg>
          </div>

          <!-- Project Info -->
          <div class="p-6">
            <h3 class="text-xl font-semibold text-white mb-2">{{ project.title }}</h3>
            <p class="text-gray text-sm mb-4 line-clamp-3">{{ project.description }}</p>

            <!-- Tags -->
            <div class="flex flex-wrap gap-2 mb-4">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="px-3 py-1 bg-primary/10 text-primary text-xs rounded-full"
              >
                {{ tag }}
              </span>
            </div>

            <!-- Links -->
            <div class="flex gap-3">
              <a
                :href="project.demo"
                class="flex-1 text-center py-2 bg-primary/10 hover:bg-primary/20 text-primary rounded-lg text-sm transition-colors"
              >
                在线演示
              </a>
              <a
                :href="project.github"
                class="flex-1 text-center py-2 border border-dark-lighter hover:border-primary text-gray hover:text-white rounded-lg text-sm transition-colors"
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
