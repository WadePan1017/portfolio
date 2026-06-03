<script setup>
import wechatQr from '../assets/wechat-qr.jpg'

const contactInfo = [
  {
    icon: '📞',
    label: '电话 / 微信',
    value: '13507943852',
    href: 'tel:13507943852',
  },
  {
    icon: '📧',
    label: '邮箱',
    value: '2455177610@qq.com',
    href: 'mailto:2455177610@qq.com',
  },
]

const platforms = [
  {
    name: '闲鱼',
    desc: '搜索「Wade Studio」',
    icon: '🐟',
  },
  {
    name: '小红书',
    desc: '搜索「Wade Studio」',
    icon: '📕',
  },
  {
    name: 'Boss直聘',
    desc: '搜索「潘伟东」',
    icon: '💼',
  },
]
</script>

<template>
  <section id="contact" class="py-24 px-6">
    <div class="max-w-4xl mx-auto text-center">
      <div class="mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          联系我们
        </h2>
        <p class="text-gray text-lg">期待与你合作，欢迎随时联系</p>
      </div>

      <div class="grid sm:grid-cols-2 gap-6 mb-12">
        <div
          v-for="info in contactInfo"
          :key="info.label"
          class="glow-card p-6 text-center"
        >
          <div class="text-3xl mb-3">{{ info.icon }}</div>
          <div class="text-sm text-gray mb-2">{{ info.label }}</div>
          <a
            :href="info.href"
            class="text-white hover:text-primary-light transition-colors font-medium"
            target="_blank"
          >
            {{ info.value }}
          </a>
        </div>
      </div>

      <!-- Platforms -->
      <div class="mb-12">
        <h3 class="text-xl font-semibold text-white mb-6">也可以在这些平台找到我们</h3>
        <div class="flex flex-wrap justify-center gap-4">
          <div
            v-for="p in platforms"
            :key="p.name"
            class="glow-card px-6 py-4 flex items-center gap-3"
          >
            <span class="text-2xl">{{ p.icon }}</span>
            <div class="text-left">
              <div class="text-white font-medium text-sm">{{ p.name }}</div>
              <div class="text-gray text-xs">{{ p.desc }}</div>
            </div>
          </div>
        </div>
      </div>

      <!-- WeChat QR -->
      <div class="glow-card p-8 inline-block">
        <h3 class="text-xl font-semibold text-white mb-4">微信扫码添加</h3>
        <img
          :src="wechatQr"
          alt="微信二维码"
          class="w-48 h-48 rounded-lg object-cover mx-auto border border-dark-border"
        />
        <p class="text-gray text-sm mt-3">扫码添加微信，备注"网站需求"更快通过</p>
      </div>
    </div>
  </section>
</template>
