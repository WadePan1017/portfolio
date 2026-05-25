<script setup>
const highlights = [
  { number: '1+', label: '年开发经验' },
  { number: '5+', label: '完成项目' },
  { number: '100%', label: '学习热情' },
]
</script>

<template>
  <section id="about" class="py-20 px-6">
    <div class="max-w-6xl mx-auto">
      <h2 class="text-3xl md:text-4xl font-bold text-white text-center mb-4">
        关于我
      </h2>
      <p class="text-gray text-center mb-12">了解我的背景和经历</p>

      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Avatar -->
        <div class="flex justify-center">
          <div class="relative">
            <div class="w-64 h-64 rounded-2xl bg-gradient-to-br from-primary to-purple-500 p-1">
              <div class="w-full h-full rounded-2xl bg-dark-light flex items-center justify-center">
                <svg class="w-24 h-24 text-primary" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
                </svg>
              </div>
            </div>
            <div class="absolute -bottom-4 -right-4 w-20 h-20 bg-primary/20 rounded-xl blur-xl"></div>
          </div>
        </div>

        <!-- Info -->
        <div>
          <h3 class="text-2xl font-semibold text-white mb-4">前端开发爱好者</h3>
          <p class="text-gray mb-6 leading-relaxed">
            我是一名热爱前端开发的应届毕业生，对构建用户友好的 Web 应用充满热情。
            虽然经验尚浅，但我有强烈的学习欲望和快速适应新技术的能力。
          </p>
          <p class="text-gray mb-8 leading-relaxed">
            我相信好的用户体验来自于对细节的关注和对技术的深入理解。
            我正在寻找一个能让我成长的前端开发岗位，期待与优秀的团队一起工作。
          </p>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-4">
            <div
              v-for="item in highlights"
              :key="item.label"
              class="text-center p-4 bg-dark-lighter/50 rounded-xl"
            >
              <div class="text-2xl font-bold text-primary mb-1">{{ item.number }}</div>
              <div class="text-sm text-gray">{{ item.label }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
