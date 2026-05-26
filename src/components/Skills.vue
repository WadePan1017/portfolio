<script setup>
const skillCategories = [
  {
    title: '前端开发',
    icon: '🌐',
    skills: [
      { name: 'HTML5', level: 80 },
      { name: 'CSS3', level: 75 },
      { name: 'JavaScript', level: 65 },
      { name: 'Vue 3', level: 60 },
    ]
  },
  {
    title: '视觉创作',
    icon: '🎬',
    skills: [
      { name: 'Premiere Pro', level: 80 },
      { name: 'Photoshop', level: 75 },
      { name: '摄影摄像', level: 70 },
      { name: '视频剪辑', level: 80 },
    ]
  },
  {
    title: '综合素质',
    icon: '💪',
    skills: [
      { name: 'Tailwind CSS', level: 65 },
      { name: 'Git 版本控制', level: 60 },
      { name: '审美与设计', level: 70 },
      { name: '团队协作', level: 75 },
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

          <div class="space-y-5">
            <div v-for="skill in category.skills" :key="skill.name">
              <div class="flex justify-between text-sm mb-2">
                <span class="text-gray-light font-medium">{{ skill.name }}</span>
                <span class="text-primary-light text-xs font-semibold">{{ skill.level }}%</span>
              </div>
              <div class="h-2 bg-dark-lighter rounded-full overflow-hidden">
                <div
                  class="h-full bg-gradient-to-r from-primary to-accent rounded-full progress-bar"
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
