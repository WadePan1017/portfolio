<script setup>
import { ref, onMounted } from 'vue'

const title = ref('')
const fullTitle = '用代码构建体验，用镜头捕捉瞬间'
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
  <section id="hero" class="min-h-screen flex items-center justify-center relative overflow-hidden pt-24">
    <!-- 极光背景光晕 -->
    <div class="absolute inset-0">
      <div class="absolute top-1/4 left-1/3 w-[500px] h-[500px] bg-primary/15 rounded-full blur-[120px]"></div>
      <div class="absolute bottom-1/3 right-1/4 w-[400px] h-[400px] bg-accent/10 rounded-full blur-[100px]"></div>
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-primary-dark/8 rounded-full blur-[150px]"></div>
    </div>

    <!-- 网格背景 -->
    <div class="absolute inset-0 opacity-[0.03]" style="background-image: linear-gradient(rgba(139, 92, 246, 0.3) 1px, transparent 1px), linear-gradient(90deg, rgba(139, 92, 246, 0.3) 1px, transparent 1px); background-size: 60px 60px;"></div>

    <div class="relative z-10 text-center px-6 max-w-4xl mx-auto">
      <div class="mb-12">
        <span class="inline-block px-5 py-2.5 bg-primary/10 border border-primary/20 rounded-full text-primary-light text-sm font-medium tracking-wide">
          欢迎来到我的个人空间
        </span>
      </div>

      <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold text-white mb-6 leading-tight">
        你好，我是<br />
        <span class="gradient-text">Wade Pan</span>
      </h1>

      <div class="text-xl md:text-2xl text-gray-light mb-8 h-8 font-light">
        {{ title }}<span :class="['text-primary', showCursor ? 'opacity-100' : 'opacity-0']">|</span>
      </div>

      <p class="text-gray max-w-2xl mx-auto mb-10 text-lg leading-relaxed">
        热爱前端开发与视觉创作，擅长将设计转化为用户体验。<br class="hidden md:block">
        同时具备摄影摄像与视频剪辑能力。
      </p>

      <!-- Key Stats -->
      <div class="flex flex-wrap justify-center gap-8 mb-12">
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">3</div>
          <div class="text-xs text-gray mt-1">上线运营网站</div>
        </div>
        <div class="w-px bg-dark-border hidden sm:block"></div>
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">2 年</div>
          <div class="text-xs text-gray mt-1">摄影行业经验</div>
        </div>
        <div class="w-px bg-dark-border hidden sm:block"></div>
        <div class="text-center">
          <div class="text-2xl font-bold gradient-text">前 5%</div>
          <div class="text-xs text-gray mt-1">本科专业排名</div>
        </div>
      </div>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#projects"
          class="group px-8 py-3.5 bg-gradient-to-r from-primary to-primary-light hover:from-primary-light hover:to-accent text-white rounded-xl font-medium transition-all shadow-lg shadow-primary/25 hover:shadow-primary/40"
        >
          查看项目
          <span class="inline-block ml-1 group-hover:translate-x-1 transition-transform">→</span>
        </a>
        <a
          href="https://github.com/WadePan1017"
          target="_blank"
          rel="noopener noreferrer"
          class="px-8 py-3.5 border border-dark-border hover:border-primary/50 text-gray hover:text-white rounded-xl font-medium transition-all hover:bg-dark-light"
        >
          <svg class="w-5 h-5 inline-block mr-2 -mt-0.5" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
          GitHub
        </a>
        <a
          href="#contact"
          class="px-8 py-3.5 border border-dark-border hover:border-primary/50 text-gray hover:text-white rounded-xl font-medium transition-all hover:bg-dark-light"
        >
          联系我
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
