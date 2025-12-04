<script setup>
import { ref } from 'vue'
import { Search, Rocket, TrendingUp, Zap, ChevronDown } from 'lucide-vue-next'

const expandedSteps = ref({})

const toggleStep = (index) => {
  expandedSteps.value[index] = !expandedSteps.value[index]
}

const steps = [
  {
    number: '01',
    icon: Search,
    title: 'Аудит и стратегия',
    shortDescription: 'Анализируем бизнес, конкурентов и формируем план действий',
    fullDescription: 'Мы анализируем ваш бизнес по всем ключевым направлениям: нишу, конкурентов, текущие продажи, качество карточек, эффективность рекламы и логистику. Определяем сильные и слабые стороны, находим точки роста и формируем прозрачный план действий.',
    benefits: [
      'детальный аудит магазинов и товаров',
      'анализ позиций относительно конкурентов',
      'оценку стоимости привлечения клиента',
      'прогноз продаж и стратегию масштабирования'
    ],
    goal: 'Цель — создать устойчивую основу для дальнейшего роста вашего бренда на маркетплейсах.'
  },
  {
    number: '02',
    icon: Rocket,
    title: 'Подготовка и запуск',
    shortDescription: 'Создаём контент, настраиваем логистику и запускаем продажи',
    fullDescription: 'Мы подготавливаем ваш магазин к полноценному входу на маркетплейсы: создаём продающий контент, улучшаем карточки товаров, настраиваем складские процессы и технические параметры.',
    benefits: [
      'оптимизация SEO и структуры карточек',
      'подготовка фото- и видео-контента',
      'настройка логистики, упаковки, маркировки',
      'подключение личного кабинета и интеграции',
      'тестовый запуск и проверка корректности работы'
    ],
    goal: 'Наша задача — чтобы старт продаж прошёл быстро, без ошибок и с максимальной отдачей.'
  },
  {
    number: '03',
    icon: TrendingUp,
    title: 'Продвижение',
    shortDescription: 'Включаем рекламу, работаем с отзывами и привлекаем трафик',
    fullDescription: 'После запуска мы включаем инструменты для активного роста продаж. Работаем с рекламой, рейтингом, отзывами и внешним трафиком, чтобы обеспечить стабильный поток покупателей.',
    benefits: [
      'настройку и оптимизацию внутренней рекламы',
      'таргетинг и привлечение внешнего трафика',
      'работу с отзывами и репутацией',
      'участие в акциях и специальных предложениях',
      'постоянный анализ продаж и корректировку стратегии'
    ],
    goal: 'Цель — вывести ваши товары в топ и обеспечить максимальный охват аудитории.'
  },
  {
    number: '04',
    icon: Zap,
    title: 'Масштабирование',
    shortDescription: 'Выстраиваем систему для роста оборота и прибыли',
    fullDescription: 'Когда магазин стабильно работает и растёт, мы выстраиваем стратегию масштабирования. Это позволяет увеличить оборот и прибыль без увеличения операционных проблем.',
    benefits: [
      'глубокий анализ данных и выявление лучших SKU',
      'оптимизацию расходов на рекламу и логистику',
      'расширение ассортимента и тестирование новых товаров',
      'автоматизацию процессов и внедрение интеграций',
      'повышение маржинальности и планирование долгосрочного роста'
    ],
    goal: 'Наша цель — превратить ваш магазин в системный, устойчивый и масштабируемый бизнес.'
  }
]
</script>

<template>
  <section class="process-timeline" id="process">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Как мы работаем</h2>
        <p class="section-subtitle">Проверенная система от запуска до масштабирования</p>
      </div>

      <div class="timeline">
        <div 
          v-for="(step, index) in steps" 
          :key="index" 
          class="timeline-item"
          :class="{ 'expanded': expandedSteps[index] }"
        >
          <!-- Timeline connector -->
          <div class="timeline-connector" v-if="index < steps.length - 1"></div>
          
          <!-- Step number badge -->
          <div class="step-badge">
            <span class="step-number">{{ step.number }}</span>
          </div>

          <!-- Step card -->
          <div class="step-card">
            <div class="step-header">
              <div class="step-icon">
                <component :is="step.icon" size="24" />
              </div>
              <div class="step-title-wrapper">
                <h3 class="step-title">{{ step.title }}</h3>
                <p class="step-short">{{ step.shortDescription }}</p>
              </div>
            </div>

            <!-- Expandable content -->
            <div class="step-content" v-show="expandedSteps[index]">
              <p class="step-description">{{ step.fullDescription }}</p>
              
              <div class="step-benefits">
                <p class="benefits-title">Вы получите:</p>
                <ul class="benefits-list">
                  <li v-for="(benefit, bIndex) in step.benefits" :key="bIndex">
                    {{ benefit }}
                  </li>
                </ul>
              </div>

              <p class="step-goal">{{ step.goal }}</p>
            </div>

            <!-- Toggle button -->
            <button 
              class="toggle-btn" 
              @click="toggleStep(index)"
              :class="{ 'active': expandedSteps[index] }"
            >
              <span>{{ expandedSteps[index] ? 'Скрыть' : 'Показать все' }}</span>
              <ChevronDown size="20" class="chevron" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.process-timeline {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-primary);
}

.timeline {
    position: relative;
    max-width: 700px;
    margin: 0 auto;
}

.timeline-item {
    position: relative;
    margin-bottom: var(--spacing-lg);
    transition: all 0.3s ease;
}

.timeline-connector {
    position: absolute;
    left: 25px;
    top: 70px;
    width: 2px;
    height: calc(100% + var(--spacing-lg));
    background: linear-gradient(180deg, var(--color-primary) 0%, transparent 100%);
    opacity: 0.3;
}

.step-badge {
    position: absolute;
    left: 0;
    top: 15px;
    width: 50px;
    height: 50px;
    background: var(--color-bg-tertiary);
    border: 2px solid var(--color-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
    transition: all 0.3s ease;
}

.timeline-item:hover .step-badge,
.timeline-item.expanded .step-badge {
    background: var(--color-primary);
    transform: scale(1.1);
    box-shadow: 0 0 20px rgba(139, 92, 246, 0.5);
}

.step-number {
    font-size: var(--font-size-xl);
    font-weight: 700;
    color: var(--color-text-primary);
    background: linear-gradient(135deg, var(--color-primary), var(--color-accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.timeline-item:hover .step-number,
.timeline-item.expanded .step-number {
    -webkit-text-fill-color: var(--color-bg-primary);
}

.step-card {
    margin-left: 70px;
    background: var(--color-bg-secondary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-md);
    transition: all 0.3s ease;
    width: 100%;
}

.timeline-item:hover .step-card,
.timeline-item.expanded .step-card {
    border-color: var(--color-primary);
    box-shadow: var(--shadow-glow);
    transform: translateX(10px);
}

.step-header {
    display: flex;
    gap: var(--spacing-sm);
    align-items: flex-start;
    margin-bottom: var(--spacing-sm);
}

.step-icon {
    width: 48px;
    height: 48px;
    background: rgba(139, 92, 246, 0.1);
    border-radius: var(--radius-md);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-primary);
    flex-shrink: 0;
    transition: all 0.3s ease;
}

.timeline-item:hover .step-icon,
.timeline-item.expanded .step-icon {
    background: var(--color-primary);
    color: var(--color-bg-primary);
    transform: rotate(5deg);
}

.step-title-wrapper {
    flex: 1;
}

.step-title {
    font-size: var(--font-size-xl);
    margin-bottom: 0.5rem;
    color: var(--color-text-primary);
}

.step-short {
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
    margin: 0;
}

.step-content {
    margin-top: var(--spacing-md);
    padding-top: var(--spacing-md);
    border-top: 1px solid var(--color-border);
    animation: slideDown 0.4s ease;
}

@keyframes slideDown {
    from {
        opacity: 0;
        transform: translateY(-10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.step-description {
    color: var(--color-text-secondary);
    line-height: 1.8;
    margin-bottom: var(--spacing-md);
}

.step-benefits {
    background: rgba(139, 92, 246, 0.05);
    border-left: 3px solid var(--color-primary);
    padding: var(--spacing-md);
    border-radius: var(--radius-sm);
    margin-bottom: var(--spacing-md);
}

.benefits-title {
    font-weight: 600;
    color: var(--color-text-primary);
    margin-bottom: var(--spacing-sm);
}

.benefits-list {
    list-style: none;
    padding: 0;
    margin: 0;
}

.benefits-list li {
    position: relative;
    padding-left: 24px;
    margin-bottom: 0.5rem;
    color: var(--color-text-secondary);
    font-size: var(--font-size-sm);
    line-height: 1.6;
}

.benefits-list li::before {
    content: '•';
    position: absolute;
    left: 8px;
    color: var(--color-primary);
    font-weight: bold;
    font-size: 1.2rem;
}

.step-goal {
    font-style: italic;
    color: var(--color-primary);
    border-left: 3px solid var(--color-primary);
    padding-left: var(--spacing-md);
    margin: 0;
    line-height: 1.6;
}

.toggle-btn {
    width: 100%;
    margin-top: var(--spacing-md);
    padding: 0.875rem;
    background: transparent;
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    color: var(--color-primary);
    font-weight: 600;
    font-size: var(--font-size-sm);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    transition: all 0.3s ease;
}

.toggle-btn:hover {
    background: rgba(139, 92, 246, 0.1);
    border-color: var(--color-primary);
    transform: translateY(-2px);
}

.toggle-btn .chevron {
    transition: transform 0.3s ease;
}

.toggle-btn.active .chevron {
    transform: rotate(180deg);
}

/* Responsive */
@media (max-width: 768px) {
    .timeline-connector {
        left: 20px;
    }
    
    .step-badge {
        width: 45px;
        height: 45px;
    }
    
    .step-number {
        font-size: var(--font-size-lg);
    }
    
    .step-card {
        margin-left: 65px;
        padding: var(--spacing-md);
    }
    
    .step-header {
        flex-direction: column;
        gap: var(--spacing-sm);
    }
    
    .timeline-item:hover .step-card,
    .timeline-item.expanded .step-card {
        transform: none;
    }
}
</style>
