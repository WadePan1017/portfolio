<script setup>
import wechatQr from '../assets/wechat-qr.jpg'

const contactInfo = [
  {
    icon: '📞',
    label: '电话',
    value: '13507943852',
    href: 'tel:13507943852',
  },
  {
    icon: '📧',
    label: '邮箱',
    value: '2455177610@qq.com',
    href: 'mailto:2455177610@qq.com',
  },
  {
    icon: '💻',
    label: 'GitHub',
    value: 'WadePan1017',
    href: 'https://github.com/WadePan1017',
  },
]
</script>

<template>
  <section id="contact" class="py-24 px-6">
    <div class="max-w-4xl mx-auto text-center">
      <div class="mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          联系我
        </h2>
        <p class="text-gray text-lg">期待与你交流，欢迎随时联系</p>
      </div>

      <div class="grid sm:grid-cols-3 gap-6 mb-12">
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

      <!-- WeChat QR Code -->
      <div class="glow-card p-8 inline-block">
        <h3 class="text-xl font-semibold text-white mb-4">微信扫码添加</h3>
        <img
          :src="wechatQr"
          alt="微信二维码"
          class="w-48 h-48 rounded-lg object-cover mx-auto border border-dark-border"
        />
        <p class="text-gray text-sm mt-3">扫码添加微信，备注"求职"更快通过</p>
      </div>
    </div>
  </section>
</template>
