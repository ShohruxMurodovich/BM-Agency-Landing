<script setup>
import { Check } from 'lucide-vue-next'

const tariffs = [
  {
    title: 'Подключ',
    subtitle: 'Для быстрого старта',
    price: 'Индивидуально',
    description: 'Стоимость зависит от количества артикулов',
    features: [
      'Анализ ниши и конкурентов',
      'Создание карточек товаров',
      'SEO-оптимизация',
      'Настройка рекламы',
      'Первая поставка'
    ],
    isPopular: false
  },
  {
    title: 'BM Flow',
    subtitle: 'Оплата за результат',
    price: '7.8%',
    label: 'от оборота',
    description: 'Вы платите только когда зарабатываете',
    features: [
      'Полное ведение кабинета',
      'Управление поставками',
      'Работа с отзывами',
      'Еженедельная отчетность',
      'Личный менеджер 24/7'
    ],
    isPopular: true
  },
  {
    title: 'BM Profit',
    subtitle: 'Партнерский',
    price: '33.3%',
    label: 'от чистой прибыли',
    description: 'Долгосрочное партнерство с разделением рисков',
    features: [
      'Стратегическое планирование',
      'Финансовый учет (P&L)',
      'Юридическая поддержка',
      'Масштабирование бизнеса',
      'Контракт на 1 год'
    ],
    isPopular: false
  }
]
</script>

<template>
  <section class="pricing" id="pricing">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Наши тарифы</h2>
        <p class="section-subtitle">Выберите модель сотрудничества, которая подходит именно вам</p>
      </div>

      <div class="pricing-grid">
        <div v-for="(tariff, index) in tariffs" :key="index" 
             class="pricing-card" :class="{ featured: tariff.isPopular }">
          
          <div v-if="tariff.isPopular" class="badge">Популярный</div>
          
          <div class="pricing-header">
            <h3 class="pricing-title">{{ tariff.title }}</h3>
            <p class="pricing-subtitle">{{ tariff.subtitle }}</p>
          </div>

          <div class="pricing-price">
            <span class="price-amount" :class="{ 'text-price': isNaN(parseFloat(tariff.price)) }">{{ tariff.price }}</span>
            <span v-if="tariff.label" class="price-label">{{ tariff.label }}</span>
            <p class="price-description">{{ tariff.description }}</p>
          </div>

          <ul class="pricing-features">
            <li v-for="(feature, fIndex) in tariff.features" :key="fIndex">
              <Check size="30" class="check-icon" />
              {{ feature }}
            </li>
          </ul>

          <a href="#contact" class="btn-primary full-width">Выбрать тариф</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pricing {
    padding: var(--spacing-xl) 0;
}

.pricing-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-md);
}

.pricing-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    position: relative;
    transition: all var(--transition-normal);
    display: flex;
    flex-direction: column;
}

.pricing-card.featured {
    border-color: var(--color-primary);
    background: linear-gradient(180deg, rgba(139, 92, 246, 0.05) 0%, var(--color-bg-tertiary) 100%);
    transform: scale(1.05);
    z-index: 2;
    box-shadow: var(--shadow-glow);
}

.pricing-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-lg);
}

.pricing-card.featured:hover {
    transform: scale(1.05) translateY(-10px);
}

.badge {
    position: absolute;
    top: -12px;
    right: 20px;
    background: var(--color-primary);
    color: var(--color-bg-primary);
    padding: 0.25rem 1rem;
    border-radius: 20px;
    font-size: var(--font-size-xs);
    font-weight: 700;
    text-transform: uppercase;
}

.pricing-header {
    text-align: center;
    margin-bottom: var(--spacing-md);
    padding-bottom: var(--spacing-md);
    border-bottom: 1px solid var(--color-border);
}

.pricing-title {
    font-size: var(--font-size-xl);
    margin-bottom: 0.5rem;
}

.pricing-subtitle {
    color: var(--color-text-secondary);
}

.pricing-price {
    text-align: center;
    margin-bottom: var(--spacing-md);
}

.price-amount {
    font-size: 3rem;
    font-weight: 800;
    display: block;
    color: var(--color-text-primary);
    background: none;
    -webkit-text-fill-color: initial;
}

.price-amount.text-price {
    font-size: 2rem;
}

.featured .price-amount {
    color: var(--color-primary);
}

.price-label {
    display: block;
    color: var(--color-text-secondary);
    font-weight: 600;
    margin-bottom: 0.5rem;
}

.price-description {
    font-size: var(--font-size-sm);
    color: var(--color-text-tertiary);
}

.pricing-features {
    margin-bottom: var(--spacing-lg);
    flex-grow: 1;
}

.pricing-features li {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1rem;
    color: var(--color-text-secondary);
    padding-left: 20px;
}

.check-icon {
    color: var(--color-primary);
    flex-shrink: 0;
}

.full-width {
    width: 100%;
    justify-content: center;
}

@media (max-width: 1024px) {
    .pricing-card.featured {
        transform: scale(1);
    }
    
    .pricing-card.featured:hover {
        transform: translateY(-10px);
    }
}
</style>
