<script setup>
const intents = [
  { icon: '💼', label: '期望岗位', value: '前端开发工程师' },
  { icon: '📍', label: '期望城市', value: '上海' },
  { icon: '📅', label: '可到岗时间', value: '随时到岗' },
  { icon: '🎓', label: '学历', value: '本科' },
]
</script>

<template>
  <section class="py-16 px-6">
    <div class="max-w-4xl mx-auto">
      <div class="glow-card p-8">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
          <div
            v-for="item in intents"
            :key="item.label"
            class="text-center"
          >
            <div class="text-2xl mb-2">{{ item.icon }}</div>
            <div class="text-xs text-gray mb-1">{{ item.label }}</div>
            <div class="text-sm text-white font-medium">{{ item.value }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
