<script setup>
const skillCategories = [
  {
    title: '前端基础',
    icon: '🌐',
    skills: [
      { name: 'HTML5', level: 85 },
      { name: 'CSS3', level: 80 },
      { name: 'JavaScript', level: 70 },
      { name: '响应式设计', level: 75 },
    ]
  },
  {
    title: '框架工具',
    icon: '⚡',
    skills: [
      { name: 'Vue 3', level: 65 },
      { name: 'Tailwind CSS', level: 75 },
      { name: 'Vite', level: 60 },
      { name: 'Git', level: 70 },
    ]
  },
  {
    title: '其他技能',
    icon: '🛠️',
    skills: [
      { name: 'Photoshop', level: 80 },
      { name: 'Premiere Pro', level: 75 },
      { name: 'Figma', level: 60 },
      { name: '团队协作', level: 70 },
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
