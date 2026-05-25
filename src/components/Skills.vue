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
  <section id="skills" class="py-20 px-6 bg-dark-light/50">
    <div class="max-w-6xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold text-white text-center mb-4">
        技能栈
      </h2>
      <p class="text-gray text-center mb-12">我掌握的技术和工具</p>

      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="category in skillCategories"
          :key="category.title"
          class="bg-dark-light border border-dark-lighter rounded-2xl p-6 hover:border-primary/30 transition-colors"
        >
          <div class="text-3xl mb-4">{{ category.icon }}</div>
          <h3 class="text-xl font-semibold text-white mb-6">{{ category.title }}</h3>

          <div class="space-y-4">
            <div v-for="skill in category.skills" :key="skill.name">
              <div class="flex justify-between text-sm mb-2">
                <span class="text-gray-light">{{ skill.name }}</span>
                <span class="text-primary">{{ skill.level }}%</span>
              </div>
              <div class="h-2 bg-dark-lighter rounded-full overflow-hidden">
                <div
                  class="h-full bg-gradient-to-r from-primary to-purple-400 rounded-full transition-all duration-1000"
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
