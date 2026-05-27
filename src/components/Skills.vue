<script setup>
const skillCategories = [
  {
    title: '前端开发',
    icon: '🌐',
    skills: [
      { name: 'HTML5', desc: '语义化标签、无障碍访问' },
      { name: 'CSS3', desc: 'Flex/Grid 布局、动画、响应式' },
      { name: 'JavaScript', desc: 'ES6+、异步编程、DOM 操作' },
      { name: 'Vue 3', desc: 'Composition API、组件封装、Pinia' },
      { name: 'Tailwind CSS', desc: '原子化样式、自定义主题' },
      { name: 'Git', desc: '分支管理、PR 工作流' },
    ]
  },
  {
    title: '视觉创作',
    icon: '🎬',
    skills: [
      { name: 'Premiere Pro', desc: '剪辑调色、多轨合成' },
      { name: 'Photoshop', desc: '修图合成、UI 素材处理' },
      { name: '摄影摄像', desc: '产品拍摄、场景构图' },
      { name: '视频剪辑', desc: '从素材到成片的完整流程' },
    ]
  },
  {
    title: '其他能力',
    icon: '💪',
    skills: [
      { name: '响应式设计', desc: '移动端优先、断点适配' },
      { name: '组件化开发', desc: '可复用组件、职责分离' },
      { name: '审美与设计', desc: '色彩搭配、排版布局' },
      { name: '团队协作', desc: '需求沟通、进度同步' },
    ]
  },
]
</script>

<template>
  <section id="skills" class="py-24 px-6 bg-dark-light/30">
    <div class="max-w-6xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          技能栈
        </h2>
        <p class="text-gray text-lg">我掌握的技术和工具</p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="category in skillCategories"
          :key="category.title"
          class="glow-card p-6"
        >
          <div class="flex items-center gap-3 mb-6">
            <span class="text-2xl">{{ category.icon }}</span>
            <h3 class="text-xl font-semibold text-white">{{ category.title }}</h3>
          </div>

          <div class="space-y-4">
            <div v-for="skill in category.skills" :key="skill.name">
              <div class="flex items-center gap-2 mb-1">
                <span class="text-white text-sm font-medium">{{ skill.name }}</span>
              </div>
              <p class="text-gray text-xs leading-relaxed">{{ skill.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
