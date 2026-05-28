<script setup>
const skillGroups = [
  {
    title: '前端开发',
    icon: '🌐',
    description: '能独立完成从品牌官网到后台管理系统的全流程开发',
    tags: ['HTML5', 'CSS3', 'JavaScript', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Element Plus', 'Pinia'],
  },
  {
    title: '视觉创作',
    icon: '🎬',
    description: '从素材采集到成片交付的完整视频制作流程',
    tags: ['Premiere Pro', 'After Effects', 'Photoshop', '摄影摄像', '视频剪辑', '调色包装'],
  },
  {
    title: '工程化',
    icon: '🛠',
    description: '熟悉现代前端工程化工具链，能独立部署上线',
    tags: ['Git', 'Vite', 'Docker', 'Node.js', 'GitHub Pages', 'Railway', 'npm'],
  },
]
</script>

<template>
  <section id="skills" class="py-24 px-6">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          技能栈
        </h2>
        <p class="text-gray text-lg">我掌握的技术和工具</p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="group in skillGroups"
          :key="group.title"
          class="glow-card p-6"
        >
          <div class="flex items-center gap-3 mb-3">
            <span class="text-2xl">{{ group.icon }}</span>
            <h3 class="text-xl font-semibold text-white">{{ group.title }}</h3>
          </div>

          <p class="text-gray text-sm mb-5 leading-relaxed">{{ group.description }}</p>

          <div class="flex flex-wrap gap-2">
            <span
              v-for="tag in group.tags"
              :key="tag"
              class="px-3 py-1.5 bg-primary/8 text-primary-light text-xs rounded-full border border-primary/10"
            >
              {{ tag }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
