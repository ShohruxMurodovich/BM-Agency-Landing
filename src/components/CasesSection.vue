<script setup>
import { TrendingUp, Zap } from 'lucide-vue-next'

const cases = [
  {
    category: 'Электроника',
    title: 'Магазин электроники',
    description: 'Увеличили оборот с 0 до 1 млрд сум всего за 3 месяца. Оптимизировали карточки, рекламу и выводили товары в топ поисковой выдачи.',
    stats: [
      { label: 'Рост продаж', value: '250%' },
      { label: 'ROI', value: '9%' }
    ],
    growth: 95
  },
  {
    category: 'Одежда',
    title: 'Бренд базовой одежды',
    description: 'Запустили магазин с нуля и получили 1200+ заказов в первый месяц. Оптимизировали карточки, улучшили контент и настроили эффективную рекламную стратегию.',
    stats: [
      { label: 'Чистая прибыль', value: '+180%' },
      { label: 'Маржинальность', value: '40%' }
    ],
    growth: 90,
    featured: true,
    highlight: 'Рекордный результат'
  },
  {
    category: 'Товары для дома',
    title: 'Магазин товаров для дома',
    description: 'Всего за три месяца оборот вырос с 11 млн до 60 млн сум. Настроили рекламные кампании, улучшили контент и увеличили поток заказов в несколько раз.',
    stats: [
      { label: 'Заказов/мес', value: '300+' },
      { label: 'Выручка', value: '70M+' }
    ],
    growth: 85
  }
]
</script>

<template>
  <section class="cases" id="cases">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Наши кейсы</h2>
        <p class="section-subtitle">Реальные результаты нашей работы</p>
      </div>

      <div class="cases-grid">
        <div v-for="(caseItem, index) in cases" :key="index" class="case-card group" :class="{ 'featured': caseItem.featured }">
          <div v-if="caseItem.featured" class="featured-badge">
            <Zap size="14" />
            <span>{{ caseItem.highlight }}</span>
          </div>
          
          <div class="case-header">
            <span class="case-category">{{ caseItem.category }}</span>
          </div>
          
          <h3 class="case-title">{{ caseItem.title }}</h3>
          <p class="case-description">{{ caseItem.description }}</p>

          <div class="case-chart-preview">
            <div class="chart-bar" style="height: 0" :data-height="caseItem.growth + '%'"></div>
            <div class="chart-line"></div>
          </div>

          <div class="case-stats" :class="{ 'stats-4': caseItem.stats.length === 4 }">
            <div v-for="(stat, sIndex) in caseItem.stats" :key="sIndex" class="case-stat">
              <span class="stat-value gradient-text">{{ stat.value }}</span>
              <span class="stat-label">{{ stat.label }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cases {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-secondary);
}

.cases-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: var(--spacing-md);
}

.case-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    transition: all var(--transition-normal);
    position: relative;
    overflow: hidden;
}

.case-card.featured {
    border-color: rgba(234, 179, 8, 0.3);
    background: linear-gradient(135deg, rgba(234, 179, 8, 0.05) 0%, var(--color-bg-tertiary) 50%);
}

.case-card.featured:hover {
    border-color: rgba(234, 179, 8, 0.6);
    box-shadow: 0 0 30px rgba(234, 179, 8, 0.2), var(--shadow-lg);
}

.featured-badge {
    position: absolute;
    top: 12px;
    right: 12px;
    background: linear-gradient(135deg, #EAB308 0%, #F59E0B 100%);
    color: #000;
    padding: 0.35rem 0.75rem;
    border-radius: 20px;
    font-size: 0.7rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 0.25rem;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    box-shadow: 0 4px 12px rgba(234, 179, 8, 0.4);
    animation: pulse-glow 2s ease-in-out infinite;
}

@keyframes pulse-glow {
    0%, 100% {
        box-shadow: 0 4px 12px rgba(234, 179, 8, 0.4);
    }
    50% {
        box-shadow: 0 4px 20px rgba(234, 179, 8, 0.6);
    }
}

.case-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-primary);
    box-shadow: var(--shadow-lg);
}

.case-header {
    margin-bottom: var(--spacing-md);
}

.case-category {
    background: rgba(59, 130, 246, 0.1);
    color: var(--color-accent);
    padding: 0.25rem 0.75rem;
    border-radius: 20px;
    font-size: var(--font-size-xs);
    font-weight: 600;
}

.case-title {
    font-size: var(--font-size-lg);
    margin-bottom: var(--spacing-sm);
}

.case-description {
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-md);
    line-height: 1.6;
}

.case-chart-preview {
    height: 100px;
    background: rgba(255, 255, 255, 0.02);
    border-radius: var(--radius-md);
    margin-bottom: var(--spacing-md);
    position: relative;
    display: flex;
    align-items: flex-end;
    padding: 0 20px;
}

.chart-bar {
    width: 100%;
    background: linear-gradient(180deg, rgba(139, 92, 246, 0.4) 0%, rgba(139, 92, 246, 0.1) 100%);
    border-top: 2px solid var(--color-primary);
    transition: height 1s ease;
}

.case-card.featured .chart-bar {
    background: linear-gradient(180deg, rgba(234, 179, 8, 0.5) 0%, rgba(234, 179, 8, 0.1) 100%);
    border-top: 2px solid #EAB308;
}

.case-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--spacing-md);
    padding-top: var(--spacing-md);
    border-top: 1px solid var(--color-border);
}

.case-stats.stats-4 {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
}

.case-stat {
    display: flex;
    flex-direction: column;
}

.stat-value {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 0.25rem;
    color: var(--color-primary);
    background: none;
    -webkit-text-fill-color: initial;
}

.case-card.featured .stat-value {
    color: #EAB308;
}

.stat-label {
    font-size: var(--font-size-xs);
    color: var(--color-text-tertiary);
}

@media (max-width: 768px) {
    .featured-badge {
        font-size: 0.65rem;
        padding: 0.3rem 0.6rem;
    }
}
</style>
