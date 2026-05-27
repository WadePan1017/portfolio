<script setup>
const skillCategories = [
  {
    title: '前端开发',
    icon: '🌐',
    skills: [
      { name: 'HTML5', level: 90 },
      { name: 'CSS3', level: 85 },
      { name: 'JavaScript', level: 80 },
      { name: 'Vue 3', level: 85 },
      { name: 'Tailwind CSS', level: 80 },
      { name: 'TypeScript', level: 65 },
    ]
  },
  {
    title: '视觉创作',
    icon: '🎬',
    skills: [
      { name: 'Premiere Pro', level: 85 },
      { name: 'After Effects', level: 70 },
      { name: 'Photoshop', level: 75 },
      { name: '摄影摄像', level: 85 },
    ]
  },
  {
    title: '其他能力',
    icon: '💪',
    skills: [
      { name: 'Git', level: 80 },
      { name: '响应式设计', level: 85 },
      { name: 'Node.js', level: 60 },
      { name: 'Docker', level: 55 },
    ]
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
              <div class="flex items-center justify-between mb-1.5">
                <span class="text-white text-sm font-medium">{{ skill.name }}</span>
                <span class="text-gray text-xs">{{ skill.level }}%</span>
              </div>
              <div class="h-1.5 bg-dark-lighter rounded-full overflow-hidden">
                <div
                  class="h-full rounded-full bg-gradient-to-r from-primary to-primary-light transition-all duration-1000"
                  :style="{ width: skill.level + '%' }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
