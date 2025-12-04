<script setup>
import { TrendingUp, ArrowUpRight } from 'lucide-vue-next'

const cases = [
  {
    category: 'Электроника',
    title: 'Магазин аксессуаров',
    description: 'Увеличили оборот с 0 до 150 млн сум за 3 месяца. Вывели 5 товаров в топ категории.',
    stats: [
      { label: 'Рост продаж', value: '+300%' },
      { label: 'ROI', value: '250%' }
    ],
    growth: 80
  },
  {
    category: 'Одежда',
    title: 'Бренд женской одежды',
    description: 'Оптимизировали расходы на рекламу и увеличили средний чек на 40%.',
    stats: [
      { label: 'Чистая прибыль', value: '+120%' },
      { label: 'Маржинальность', value: '35%' }
    ],
    growth: 65
  },
  {
    category: 'Товары для дома',
    title: 'Home Decor',
    description: 'Запуск с нуля. Через 2 месяца вышли на окупаемость и начали масштабирование.',
    stats: [
      { label: 'Заказов/мес', value: '500+' },
      { label: 'Выручка', value: '80M+' }
    ],
    growth: 90
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
        <div v-for="(caseItem, index) in cases" :key="index" class="case-card group">
          <div class="case-header">
            <span class="case-category">{{ caseItem.category }}</span>
            <button class="case-link">
              <ArrowUpRight size="20" />
            </button>
          </div>
          
          <h3 class="case-title">{{ caseItem.title }}</h3>
          <p class="case-description">{{ caseItem.description }}</p>

          <div class="case-chart-preview">
            <div class="chart-bar" style="height: 0" :data-height="caseItem.growth + '%'"></div>
            <div class="chart-line"></div>
          </div>

          <div class="case-stats">
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

.case-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-primary);
    box-shadow: var(--shadow-lg);
}

.case-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
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

.case-link {
    background: rgba(255, 255, 255, 0.05);
    border: none;
    color: var(--color-text-primary);
    width: 36px;
    height: 36px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: var(--transition-fast);
}

.case-card:hover .case-link {
    background: var(--color-primary);
    color: var(--color-bg-primary);
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

.case-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--spacing-md);
    padding-top: var(--spacing-md);
    border-top: 1px solid var(--color-border);
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

.stat-label {
    font-size: var(--font-size-xs);
    color: var(--color-text-tertiary);
}
</style>
