<script setup>
const contactInfo = [
  {
    icon: '📧',
    label: '邮箱',
    value: '2455177610@qq.com',
    href: 'mailto:2455177610@qq.com',
  },
  {
    icon: '💻',
    label: 'GitHub',
    value: 'github.com/pan245517-arch',
    href: 'https://github.com/pan245517-arch',
  },
  {
    icon: '📍',
    label: '所在地',
    value: '上海',
    href: null,
  },
]
</script>

<template>
  <section id="contact" class="py-20 px-6 bg-dark-light/50">
    <div class="max-w-4xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
        联系我
      </h2>
      <p class="text-gray mb-12">有合作机会或想聊聊？欢迎联系我</p>

      <div class="grid sm:grid-cols-3 gap-6 mb-12">
        <div
          v-for="info in contactInfo"
          :key="info.label"
          class="bg-dark-light border border-dark-lighter rounded-2xl p-6 hover:border-primary/30 transition-colors"
        >
          <div class="text-3xl mb-3">{{ info.icon }}</div>
          <div class="text-sm text-gray mb-1">{{ info.label }}</div>
          <a
            v-if="info.href"
            :href="info.href"
            class="text-white hover:text-primary transition-colors"
            target="_blank"
          >
            {{ info.value }}
          </a>
          <div v-else class="text-white">{{ info.value }}</div>
        </div>
      </div>

      <div class="bg-dark-light border border-dark-lighter rounded-2xl p-8">
        <h3 class="text-xl font-semibold text-white mb-4">给我发消息</h3>
        <form class="space-y-4" @submit.prevent>
          <div class="grid sm:grid-cols-2 gap-4">
            <input
              type="text"
              placeholder="你的名字"
              class="w-full px-4 py-3 bg-dark-lighter border border-dark-lighter rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary transition-colors"
            />
            <input
              type="email"
              placeholder="你的邮箱"
              class="w-full px-4 py-3 bg-dark-lighter border border-dark-lighter rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary transition-colors"
            />
          </div>
          <textarea
            rows="4"
            placeholder="你的消息..."
            class="w-full px-4 py-3 bg-dark-lighter border border-dark-lighter rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary transition-colors resize-none"
          ></textarea>
          <button
            type="submit"
            class="w-full sm:w-auto px-8 py-3 bg-primary hover:bg-primary-light text-white rounded-lg font-medium transition-colors"
          >
            发送消息
          </button>
        </form>
      </div>
    </div>
  </section>
</template>
