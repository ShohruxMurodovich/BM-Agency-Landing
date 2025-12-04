<script setup>
import { Percent, Award, Settings, BarChart2, TrendingUp, Shield, UserCog, Cpu } from 'lucide-vue-next'

const advantages = [
  {
    icon: Percent,
    title: 'Оплата за результат',
    description: 'Мы зарабатываем только тогда, когда зарабатываете вы. Честные 7.8% от оборота.'
  },
  {
    icon: Award,
    title: '5+ лет опыта',
    description: 'Знаем все тонкости работы на маркетплейсах и умеем обходить подводные камни.'
  },
  {
    icon: Settings,
    title: 'Полный аутсорсинг',
    description: 'Берем на себя всю рутину: от создания карточек до логистики и общения с клиентами.'
  },
  {
    icon: BarChart2,
    title: 'Прозрачная аналитика',
    description: 'Предоставляем подробные отчеты о продажах, расходах и чистой прибыли.'
  },
  {
    icon: TrendingUp,
    title: 'Быстрый старт',
    description: 'Запускаем продажи в кратчайшие сроки благодаря отлаженным процессам.'
  },
  {
    icon: Shield,
    title: 'Безопасность',
    description: 'Гарантируем сохранность ваших данных и товаров. Работаем по договору.'
  },
  {
    icon: UserCog,
    title: 'Индивидуальный подход',
    description: 'Персональная стратегия и менеджер под ваш бизнес — никаких шаблонных решений.'
  },
  {
    icon: Cpu,
    title: 'Технологичность и автоматизация',
    description: 'Используем современные инструменты и интеграции, чтобы ускорять процессы и снижать ошибки.'
  }
]
</script>

<template>
  <section class="advantages" id="advantages">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Почему выбирают нас</h2>
        <p class="section-subtitle">Наши преимущества — ваш успех</p>
      </div>

      <div class="advantages-grid">
        <div v-for="(advantage, index) in advantages" :key="index" class="advantage-card">
          <div class="advantage-icon">
            <component :is="advantage.icon" size="32" />
          </div>
          <h3>{{ advantage.title }}</h3>
          <p>{{ advantage.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.advantages {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-primary);
}

.advantages-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-md);
}

.advantage-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    text-align: center;
    transition: all var(--transition-normal);
}

.advantage-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-primary);
    box-shadow: var(--shadow-lg);
}

.advantage-icon {
    width: 64px;
    height: 64px;
    background: rgba(0, 220, 130, 0.1);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-primary);
    margin: 0 auto var(--spacing-md);
    transition: var(--transition-normal);
}

.advantage-card:hover .advantage-icon {
    background: var(--color-primary);
    color: var(--color-bg-primary);
    transform: scale(1.1);
}

.advantage-card h3 {
    margin-bottom: var(--spacing-sm);
    font-size: var(--font-size-md);
}

.advantage-card p {
    color: var(--color-text-secondary);
    font-size: var(--font-size-sm);
    margin: 0;
}
</style>
