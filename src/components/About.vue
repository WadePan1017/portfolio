<script setup>
import avatar from '../assets/avatar.png'

const highlights = [
  { number: '6+', label: '掌握技能' },
  { number: '2', label: '跨领域能力' },
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
              <div class="w-full h-full rounded-2xl bg-dark-light overflow-hidden">
                <img :src="avatar" alt="Wade Pan" class="w-full h-full object-cover" />
              </div>
            </div>
            <div class="absolute -bottom-4 -right-4 w-20 h-20 bg-primary/20 rounded-xl blur-xl"></div>
          </div>
        </div>

        <!-- Info -->
        <div>
          <h3 class="text-2xl font-semibold text-white mb-4">Wade Pan / 潘伟东</h3>
          <p class="text-gray mb-6 leading-relaxed">
            我是一名兼具前端开发与视觉创作能力的应届毕业生。在前端方面，我掌握
            HTML、CSS、JavaScript 和 Vue 框架，能够独立完成响应式网站的开发；
            在视觉方面，我擅长摄影摄像和视频剪辑，能用 Premiere Pro 和 Photoshop
            完成从素材采集到成片的完整流程。
          </p>
          <p class="text-gray mb-8 leading-relaxed">
            我相信技术与审美的结合能创造出更好的产品体验。我正在寻找一个前端开发岗位，
            期待能将我的跨领域技能发挥到工作中，与团队一起打造优秀的产品。
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
