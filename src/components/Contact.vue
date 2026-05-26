<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')
const sent = ref(false)

function handleSubmit() {
  if (!message.value.trim()) return

  const subject = `来自 ${name.value || '访客'} 的留言 - 作品集`
  const body = `发送者：${name.value || '未填写'}
邮箱：${email.value || '未填写'}

留言内容：
${message.value}
`
  window.location.href = `mailto:2455177610@qq.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`
  sent.value = true
}

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
    value: 'github.com/WadePan1017',
    href: 'https://github.com/WadePan1017',
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
  <section id="contact" class="py-24 px-6 bg-dark-light/30">
    <div class="max-w-4xl mx-auto text-center">
      <div class="mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          联系我
        </h2>
        <p class="text-gray text-lg">有合作机会或想聊聊？欢迎联系我</p>
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
            v-if="info.href"
            :href="info.href"
            class="text-white hover:text-primary-light transition-colors font-medium"
            target="_blank"
          >
            {{ info.value }}
          </a>
          <div v-else class="text-white font-medium">{{ info.value }}</div>
        </div>
      </div>

      <div class="glow-card p-8">
        <h3 class="text-xl font-semibold text-white mb-6">给我发消息</h3>
        <form class="space-y-4" @submit.prevent="handleSubmit">
          <div class="grid sm:grid-cols-2 gap-4">
            <input
              v-model="name"
              type="text"
              placeholder="你的名字"
              class="w-full px-4 py-3 bg-dark-lighter border border-dark-border rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary/50 transition-colors"
            />
            <input
              v-model="email"
              type="email"
              placeholder="你的邮箱"
              class="w-full px-4 py-3 bg-dark-lighter border border-dark-border rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary/50 transition-colors"
            />
          </div>
          <textarea
            v-model="message"
            rows="4"
            placeholder="你的消息..."
            class="w-full px-4 py-3 bg-dark-lighter border border-dark-border rounded-lg text-white placeholder-gray focus:outline-none focus:border-primary/50 transition-colors resize-none"
          ></textarea>
          <div class="flex items-center gap-4">
            <button
              type="submit"
              class="px-8 py-3 bg-gradient-to-r from-primary to-primary-light hover:from-primary-light hover:to-accent text-white rounded-lg font-medium transition-all shadow-lg shadow-primary/20 hover:shadow-primary/30"
            >
              发送消息
            </button>
            <span v-if="sent" class="text-green-400 text-sm">邮件客户端已打开，请发送邮件即可</span>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>
