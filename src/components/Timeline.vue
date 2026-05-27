<script setup>
const events = [
  {
    year: '2019',
    title: '军旅淬炼',
    description: '服役于 92569 部队，担任文书兼通讯员，负责公文写作、档案管理及摄影摄像工作，锤炼执行力与抗压能力。',
    icon: '🎖️',
  },
  {
    year: '2021',
    title: '求学深造',
    description: '就读江西工业工程职业技术学院数字媒体技术专业，系统学习摄影摄像、影视后期及网页设计，专业排名前 5%。',
    icon: '📚',
  },
  {
    year: '2024',
    title: '摄影与前端并行',
    description: '入职温州清晨文化担任摄影摄像师，独立负责产品、活动、展会的视频拍摄与后期制作；同时独立完成正日移门、非凡大师等品牌官网开发，从需求对接到上线全程负责，摄影与前端双线成长。',
    icon: '⚡',
  },
  {
    year: '2024',
    title: '升入本科',
    description: '考入景德镇陶瓷大学数字媒体艺术设计专业，深入学习网页设计、流媒体技术与影视特效，专业排名前 5%。',
    icon: '🎨',
  },
  {
    year: '2026',
    title: '摄影与前端双线发展',
    description: '入职上海志磐体育文化担任拍摄，负责团建徒步、户外活动全程摄影摄像，涵盖活动记录、人物跟拍、环境特写；独立完成视频后期剪辑、调色、音效与字幕包装。同步运营公司抖音、小红书账号，提升账号活跃度。在户外项目中兼任带队教练，实现"一岗多能"。获客户好评"摄影专业、沟通顺畅、出片快"，被公司评为多面手员工。',
    icon: '✨',
  },
]
</script>

<template>
  <section id="timeline" class="py-24 px-6">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
          成长经历
        </h2>
        <p class="text-gray text-lg">我的学习与实践之路</p>
      </div>

      <div class="relative">
        <!-- Center line -->
        <div class="absolute left-6 md:left-1/2 md:-translate-x-px top-0 bottom-0 w-0.5 bg-gradient-to-b from-primary via-accent to-primary/20"></div>

        <div class="space-y-12">
          <div
            v-for="(event, index) in events"
            :key="index"
            :class="[
              'relative flex items-start gap-6',
              index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse',
            ]"
          >
            <!-- Dot -->
            <div class="absolute left-6 md:left-1/2 -translate-x-1/2 w-12 h-12 rounded-full bg-dark-light border-2 border-primary flex items-center justify-center text-lg z-10 shadow-lg shadow-primary/20">
              {{ event.icon }}
            </div>

            <!-- Card -->
            <div :class="[
              'ml-16 md:ml-0 md:w-[calc(50%-2.5rem)]',
              index % 2 === 0 ? 'md:pr-0' : 'md:pl-0',
            ]">
              <div class="glow-card p-5">
                <span class="text-sm font-semibold text-primary-light tracking-wider">{{ event.year }}</span>
                <h3 class="text-lg font-semibold text-white mt-1 mb-2">{{ event.title }}</h3>
                <p class="text-gray text-sm leading-relaxed">{{ event.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
