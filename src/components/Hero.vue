<script setup>
import { ref, onMounted } from 'vue'

const title = ref('')
const fullTitle = '企业官网制作 · 个人网站开发 · 后台系统开发'
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
  }, 80)

  setInterval(() => {
    showCursor.value = !showCursor.value
  }, 530)
})
</script>

<template>
  <section id="hero" class="min-h-screen flex items-center justify-center relative overflow-hidden pt-24">
    <!-- Background glow -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 left-1/3 w-[500px] h-[500px] bg-primary/15 rounded-full blur-[120px]"></div>
      <div class="absolute bottom-1/3 right-1/4 w-[400px] h-[400px] bg-accent/10 rounded-full blur-[100px]"></div>
    </div>

    <!-- Grid background -->
    <div class="absolute inset-0 opacity-[0.03]" style="background-image: linear-gradient(rgba(139, 92, 246, 0.3) 1px, transparent 1px), linear-gradient(90deg, rgba(139, 92, 246, 0.3) 1px, transparent 1px); background-size: 60px 60px;"></div>

    <div class="relative z-10 text-center px-6 max-w-4xl mx-auto">
      <div class="mb-8">
        <span class="inline-block px-5 py-2.5 bg-primary/10 border border-primary/20 rounded-full text-primary-light text-sm font-medium tracking-wide">
          Wade Studio 网站开发工作室
        </span>
      </div>

      <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold text-white mb-6 leading-tight">
        企业官网制作<br />
        <span class="gradient-text">3天快速交付</span>
      </h1>

      <div class="text-xl md:text-2xl text-gray-light mb-8 h-8 font-light">
        {{ title }}<span :class="['text-primary', showCursor ? 'opacity-100' : 'opacity-0']">|</span>
      </div>

      <p class="text-gray max-w-2xl mx-auto mb-10 text-lg leading-relaxed">
        企业官网 · 个人网站 · 后台系统<br class="hidden md:block">
        599元起 | 3天快速交付 | 支持部署上线
      </p>

      <!-- Key Stats -->
      <div class="flex flex-wrap justify-center gap-8 mb-12">
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">5+</div>
          <div class="text-xs text-gray mt-1">已上线网站</div>
        </div>
        <div class="w-px bg-dark-border hidden sm:block"></div>
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">3天</div>
          <div class="text-xs text-gray mt-1">最快交付</div>
        </div>
        <div class="w-px bg-dark-border hidden sm:block"></div>
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">100%</div>
          <div class="text-xs text-gray mt-1">源码交付</div>
        </div>
      </div>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#pricing"
          class="group px-8 py-3.5 bg-gradient-to-r from-primary to-primary-light hover:from-primary-light hover:to-accent text-white rounded-xl font-medium transition-all shadow-lg shadow-primary/25 hover:shadow-primary/40"
        >
          查看报价
          <span class="inline-block ml-1 group-hover:translate-x-1 transition-transform">→</span>
        </a>
        <a
          href="#contact"
          class="px-8 py-3.5 border border-dark-border hover:border-primary/50 text-gray hover:text-white rounded-xl font-medium transition-all hover:bg-dark-light"
        >
          联系我们
        </a>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-gray" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </div>
  </section>
</template>
