<script setup>
import { ref, onMounted } from 'vue'

const title = ref('')
const fullTitle = '前端开发工程师'
const showCursor = ref(true)

onMounted(() => {
  let i = 0
  const timer = setInterval(() => {
    if (i < fullTitle.length) {
      title.value += fullTitle[i]
      i++
    } else {
      clearInterval(timer)
    }
  }, 100)

  setInterval(() => {
    showCursor.value = !showCursor.value
  }, 530)
})
</script>

<template>
  <section id="hero" class="min-h-screen flex items-center justify-center relative overflow-hidden">
    <!-- Background Effect -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-primary/10 rounded-full blur-3xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-purple-500/10 rounded-full blur-3xl"></div>
    </div>

    <div class="relative z-10 text-center px-6">
      <div class="mb-6">
        <span class="inline-block px-4 py-2 bg-primary/10 border border-primary/20 rounded-full text-primary text-sm">
          欢迎来到我的个人空间
        </span>
      </div>

      <h1 class="text-5xl md:text-7xl font-bold text-white mb-4">
        你好，我是
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-purple-400">
          开发者
        </span>
      </h1>

      <div class="text-xl md:text-2xl text-gray mb-8 h-8">
        {{ title }}<span :class="['text-primary', showCursor ? 'opacity-100' : 'opacity-0']">|</span>
      </div>

      <p class="text-gray max-w-xl mx-auto mb-10 text-lg">
        热爱前端开发，专注于构建优秀的用户体验。<br>
        使用 Vue、Tailwind CSS 等现代技术栈。
      </p>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#projects"
          class="px-8 py-3 bg-primary hover:bg-primary-light text-white rounded-lg font-medium transition-colors"
          @click.prevent="$el.querySelector('a').scrollIntoView({ behavior: 'smooth' })"
        >
          查看项目
        </a>
        <a
          href="#contact"
          class="px-8 py-3 border border-dark-lighter hover:border-primary text-gray hover:text-white rounded-lg font-medium transition-colors"
        >
          联系我
        </a>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-gray" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </div>
  </section>
</template>
