<script setup>
import { Store, BarChart3, Truck, Code2, ArrowRight } from 'lucide-vue-next'

const services = [
  {
    icon: Store,
    title: 'Полное управление',
    description: 'Берем на себя все процессы: от регистрации до ежедневного управления продажами.',
    features: ['Регистрация кабинета', 'Создание карточек', 'SEO оптимизация', 'Работа с отзывами']
  },
  {
    icon: BarChart3,
    title: 'Продвижение и реклама',
    description: 'Настройка эффективных рекламных кампаний для максимального охвата.',
    features: ['Внутренняя реклама', 'Внешний трафик', 'Участие в акциях', 'Аналитика продаж']
  },
  {
    icon: Truck,
    title: 'Логистика и склад',
    description: 'Полный цикл фулфилмента. Хранение, упаковка и доставка товаров.',
    features: ['Приемка товара', 'Упаковка и маркировка', 'Отгрузка на МП', 'Работа с возвратами']
  },
  {
    icon: Code2,
    title: 'IT-Разработка',
    description: 'Создание сайтов и Telegram-ботов для автоматизации вашего бизнеса.',
    features: ['Интернет-магазины', 'Telegram-боты', 'Интеграции', 'Техническая поддержка']
  }
]
</script>

<template>
  <section class="services" id="services">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Наши услуги</h2>
        <p class="section-subtitle">Комплексные решения для вашего бизнеса</p>
      </div>

      <div class="services-grid">
        <div v-for="(service, index) in services" :key="index" class="service-card group">
          <div class="service-icon-wrapper">
            <component :is="service.icon" size="32" />
          </div>
          
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-description">{{ service.description }}</p>
          
          <ul class="service-features">
            <li v-for="(feature, fIndex) in service.features" :key="fIndex">
              <div class="dot"></div>
              {{ feature }}
            </li>
          </ul>

          <div class="service-footer">
            <span class="learn-more">
              Подробнее <ArrowRight size="16" />
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
    padding: var(--spacing-xl) 0;
}

.services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-md);
}

.service-card {
    background: var(--color-bg-secondary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    transition: all var(--transition-normal);
    position: relative;
    overflow: hidden;
    height: 100%;
    display: flex;
    flex-direction: column;
}

.service-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-primary);
    box-shadow: var(--shadow-lg);
}

.service-icon-wrapper {
    width: 64px;
    height: 64px;
    background: var(--color-bg-tertiary);
    border-radius: var(--radius-md);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-primary);
    margin-bottom: var(--spacing-md);
    transition: var(--transition-normal);
}

.service-card:hover .service-icon-wrapper {
    background: var(--color-primary);
    color: var(--color-bg-primary);
}

.service-title {
    font-size: var(--font-size-lg);
    margin-bottom: var(--spacing-sm);
}

.service-description {
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-md);
    flex-grow: 1;
}

.service-features {
    margin-bottom: var(--spacing-md);
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.service-features li {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    color: var(--color-text-tertiary);
    font-size: var(--font-size-sm);
}

.dot {
    width: 6px;
    height: 6px;
    background: var(--color-primary);
    border-radius: 50%;
    opacity: 0.5;
}

.service-footer {
    margin-top: auto;
}

.learn-more {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    color: var(--color-primary);
    font-weight: 600;
    font-size: var(--font-size-sm);
    opacity: 0;
    transform: translateX(-10px);
    transition: all var(--transition-normal);
}

.service-card:hover .learn-more {
    opacity: 1;
    transform: translateX(0);
}
</style>
