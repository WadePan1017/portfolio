<script setup>
import { computed, ref } from 'vue'
import {
  ArrowUpRight,
  CheckCircle2,
  Code2,
  FileText,
  LayoutDashboard,
  MessageCircle,
  Rocket,
  ShieldCheck,
  Sparkles,
  Wrench,
  PenTool,
  Send,
  Headphones,
} from 'lucide-vue-next'

import projectAi from './assets/project-ai-tools.png'
import projectFurniture from './assets/project-furniture.png'
import projectAdmin from './assets/project-admin.png'
import projectZrzr from './assets/project-zrzr.png'
import casePortfolio from './assets/case-portfolio.png'
import caseEducation from './assets/case-education.png'
import caseRestaurant from './assets/case-restaurant.png'
import caseLaw from './assets/case-law.png'
import caseRenovation from './assets/case-renovation.png'

const navItems = ['首页', '服务', '案例', '流程', '报价', '联系']

const services = [
  {
    icon: LayoutDashboard,
    title: '企业官网',
    desc: '品牌介绍、服务展示、客户咨询入口一次搭好',
  },
  {
    icon: FileText,
    title: '个人主页',
    desc: '适合自由职业者、主理人、设计师和技术个人',
  },
  {
    icon: Code2,
    title: '后台管理',
    desc: '数据录入、内容管理、权限控制和业务看板',
  },
  {
    icon: Rocket,
    title: '定制开发',
    desc: '按真实业务流程开发，不堆没用的功能',
  },
  {
    icon: Wrench,
    title: '维护优化',
    desc: '上线后可继续做页面调整、功能迭代和性能优化',
  },
]

const activeCaseFilter = ref('精选')

const caseFilters = ['精选', '全部案例', '官网', '工具', '后台', '行业模板']

const cases = [
  {
    title: '品牌官网改版',
    type: '官网',
    desc: '重新整理首页结构、产品卖点和咨询路径，让访客更快理解业务。',
    image: projectFurniture,
    tags: ['官网改版', '移动端适配', '咨询转化'],
    demo: 'http://www.topr8.cn/',
    featured: true,
  },
  {
    title: 'AI 工具导航站',
    type: '工具',
    desc: '把工具分类、搜索、标签和卡片展示做成可长期维护的站点。',
    image: projectAi,
    tags: ['Vue', '搜索筛选', '内容管理'],
    demo: 'https://WadePan1017.github.io/ai-tools-site/',
    featured: true,
  },
  {
    title: '企业形象官网',
    type: '官网',
    desc: '围绕品牌调性设计页面视觉，完成从前端开发到部署上线。',
    image: projectZrzr,
    tags: ['品牌视觉', '多页面', '上线部署'],
    demo: 'http://www.zrzr.top/',
    featured: true,
  },
  {
    title: '业务管理后台',
    type: '后台',
    desc: '搭建数据看板、下载记录、用户管理等高频后台工作流。',
    image: projectAdmin,
    tags: ['数据看板', '权限管理', '业务流程'],
    demo: 'https://just-fulfillment-production-d6a9.up.railway.app/',
    featured: true,
  },
  {
    title: 'Wade Studio 官网',
    type: '官网',
    desc: '网站开发服务页，包含服务介绍、报价、案例展示和咨询入口。',
    image: casePortfolio,
    tags: ['服务页', '报价展示', '咨询入口'],
    demo: 'https://WadePan1017.github.io/portfolio/',
  },
  {
    title: '教育培训官网',
    type: '行业模板',
    desc: '课程体系、师资介绍、价格方案和报名咨询页面组合。',
    image: caseEducation,
    tags: ['课程展示', '报名咨询', '响应式'],
    demo: 'cases/education.html',
  },
  {
    title: '餐饮品牌官网',
    type: '行业模板',
    desc: '菜单展示、门店环境、预约订座和用户评价模块。',
    image: caseRestaurant,
    tags: ['菜单展示', '预约表单', '门店介绍'],
    demo: 'cases/restaurant.html',
  },
  {
    title: '律所官网模板',
    type: '行业模板',
    desc: '服务领域、律师团队、案例说明和在线咨询结构。',
    image: caseLaw,
    tags: ['服务领域', '团队展示', '在线咨询'],
    demo: 'cases/law.html',
  },
  {
    title: '装修公司官网',
    type: '行业模板',
    desc: '装修案例、设计团队、服务流程和报价收集表单。',
    image: caseRenovation,
    tags: ['案例展示', '报价表单', '服务流程'],
    demo: 'cases/renovation.html',
  },
]

const visibleCases = computed(() => {
  if (activeCaseFilter.value === '精选') {
    return cases.filter((item) => item.featured)
  }

  if (activeCaseFilter.value === '全部案例') {
    return cases
  }

  return cases.filter((item) => item.type === activeCaseFilter.value)
})

const pricing = [
  {
    name: '基础展示页',
    price: '599',
    items: ['1-3 个页面', '响应式适配', '部署上线'],
  },
  {
    name: '标准官网',
    price: '999',
    badge: '推荐',
    items: ['5 个页面以内', '视觉定制', '基础 SEO'],
  },
  {
    name: '定制功能',
    price: '1999',
    items: ['按需求开发', '表单 / 后台 / 数据', '源码交付'],
  },
]

const process = [
  { icon: MessageCircle, no: '01', title: '需求沟通', desc: '确认目标和内容' },
  { icon: PenTool, no: '02', title: '页面方案', desc: '确定结构和风格' },
  { icon: Code2, no: '03', title: '开发实现', desc: '前端与功能开发' },
  { icon: Send, no: '04', title: '测试上线', desc: '检查并部署' },
  { icon: Headphones, no: '05', title: '售后调整', desc: '上线后继续优化' },
]

function scrollToSection(label) {
  const map = {
    首页: 'top',
    服务: 'services',
    案例: 'cases',
    流程: 'process',
    报价: 'pricing',
    联系: 'contact',
  }
  document.getElementById(map[label])?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <main id="top" class="site-shell">
    <aside class="intro-panel">
      <div class="intro-inner">
        <a class="brand" href="#top" aria-label="Wade Studio 首页">Wade Studio</a>
        <p class="brand-subtitle">网站开发者 / 数字产品构建者</p>

        <section class="hero-copy">
          <p class="eyebrow">专注网站开发 · 适合小团队、个体商家和独立创作者</p>
          <h1>把业务讲清楚，<br />让客户来咨询</h1>
          <p class="lead">
            网站不是只放几张图。先把业务、服务和信任感讲清楚，再把手机适配、访问速度和咨询入口做好，
            让客户看完知道下一步该怎么联系你。
          </p>
        </section>

        <div class="service-list" id="services">
          <article v-for="item in services" :key="item.title" class="service-item">
            <component :is="item.icon" :size="22" stroke-width="1.8" />
            <div>
              <h2>{{ item.title }}</h2>
              <p>{{ item.desc }}</p>
            </div>
          </article>
        </div>

        <div class="intro-actions">
          <a class="primary-button" href="#contact">
            咨询我的项目
            <ArrowUpRight :size="17" />
          </a>
          <button class="ghost-button" type="button" @click="activeCaseFilter = '全部案例'; scrollToSection('案例')">
            查看全部案例
          </button>
        </div>

        <dl class="stats">
          <div>
            <dt>3+</dt>
            <dd>独立开发经验</dd>
          </div>
          <div>
            <dt>60+</dt>
            <dd>项目交付</dd>
          </div>
          <div>
            <dt>7天</dt>
            <dd>售后调整</dd>
          </div>
        </dl>

        <footer class="side-footer">
          <span>© 2024 Wade Studio. 保留所有权利。</span>
          <span>中国 · 杭州</span>
        </footer>
      </div>
    </aside>

    <section class="work-panel">
      <header class="topbar">
        <nav aria-label="主导航">
          <button
            v-for="item in navItems"
            :key="item"
            type="button"
            @click="scrollToSection(item)"
          >
            {{ item }}
          </button>
        </nav>
        <a class="text-link" href="#contact">
          预约沟通
          <ArrowUpRight :size="15" />
        </a>
      </header>

      <section id="cases" class="case-section">
        <div class="case-heading">
          <div>
            <p>Selected Work</p>
            <h2>{{ activeCaseFilter === '精选' ? '首页精选案例' : activeCaseFilter }}</h2>
          </div>
          <div class="filter-row" aria-label="案例分类">
            <button
              v-for="filter in caseFilters"
              :key="filter"
              type="button"
              :class="{ active: activeCaseFilter === filter }"
              @click="activeCaseFilter = filter"
            >
              {{ filter }}
            </button>
          </div>
        </div>

        <div class="case-list">
          <a
            v-for="item in visibleCases"
            :key="item.title"
            class="case-card"
            :href="item.demo"
            target="_blank"
            rel="noopener noreferrer"
          >
            <div class="case-image">
              <img :src="item.image" :alt="item.title" loading="lazy" />
            </div>
            <div class="case-meta">
              <span>{{ item.type }}</span>
              <h3>{{ item.title }}</h3>
              <p>{{ item.desc }}</p>
              <div class="case-tags">
                <span v-for="tag in item.tags" :key="tag">{{ tag }}</span>
              </div>
            </div>
            <ArrowUpRight class="case-arrow" :size="18" />
          </a>
        </div>
      </section>

      <section class="bottom-panel">
        <section id="pricing" class="pricing-block">
          <div class="section-heading">
            <div>
              <h2>服务价格</h2>
              <p>先把预算压下来，按真实需求加功能</p>
            </div>
            <a href="#contact">获取报价 <ArrowUpRight :size="14" /></a>
          </div>

          <div class="pricing-grid">
            <article
              v-for="item in pricing"
              :key="item.name"
              :class="['price-card', item.badge ? 'featured' : '']"
            >
              <span v-if="item.badge" class="badge">{{ item.badge }}</span>
              <h3>{{ item.name }}</h3>
              <p class="price">¥ {{ item.price }} <small>起</small></p>
              <ul>
                <li v-for="line in item.items" :key="line">
                  <CheckCircle2 :size="14" />
                  {{ line }}
                </li>
              </ul>
            </article>
          </div>
        </section>

        <section id="process" class="process-block">
          <div class="section-heading">
            <div>
              <h2>项目流程</h2>
              <p>少开会，多交付，节点清楚</p>
            </div>
            <a href="#contact">了解流程 <ArrowUpRight :size="14" /></a>
          </div>

          <div class="process-line">
            <article v-for="item in process" :key="item.no" class="process-item">
              <div class="process-icon">
                <component :is="item.icon" :size="25" stroke-width="1.8" />
              </div>
              <span>{{ item.no }}</span>
              <h3>{{ item.title }}</h3>
              <p>{{ item.desc }}</p>
            </article>
          </div>
        </section>
      </section>

      <section id="contact" class="contact-strip">
        <div>
          <Sparkles :size="18" />
          <span>可接新项目</span>
        </div>
        <a href="tel:13507943852">电话 / 微信：13507943852</a>
        <a href="mailto:2455177610@qq.com">2455177610@qq.com</a>
        <div>
          <ShieldCheck :size="18" />
          <span>源码交付 · 部署上线 · 售后支持</span>
        </div>
      </section>
    </section>
  </main>
</template>
