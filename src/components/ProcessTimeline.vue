<script setup>
const steps = [
  {
    number: '01',
    title: 'Аудит и стратегия',
    description: 'Проводим глубокий анализ вашей ниши, конкурентов и текущих показателей. Разрабатываем персональную стратегию роста.'
  },
  {
    number: '02',
    title: 'Подготовка и запуск',
    description: 'Создаем продающий контент, оптимизируем карточки товаров, настраиваем логистику и запускаем магазин.'
  },
  {
    number: '03',
    title: 'Продвижение',
    description: 'Запускаем рекламные кампании, работаем с отзывами и рейтингом, привлекаем внешний трафик.'
  },
  {
    number: '04',
    title: 'Масштабирование',
    description: 'Анализируем результаты, оптимизируем расходы и расширяем ассортимент для кратного роста прибыли.'
  }
]
</script>

<template>
  <section class="process" id="process">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Как мы работаем</h2>
        <p class="section-subtitle">Прозрачный путь к вашему успеху</p>
      </div>

      <div class="process-timeline">
        <div v-for="(step, index) in steps" :key="index" class="timeline-item">
          <div class="timeline-number">{{ step.number }}</div>
          <div class="timeline-content">
            <h3>{{ step.title }}</h3>
            <p>{{ step.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.process {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-primary);
}

.process-timeline {
    max-width: 800px;
    margin: 0 auto;
    position: relative;
}

.process-timeline::before {
    content: '';
    position: absolute;
    left: 30px;
    top: 0;
    bottom: 0;
    width: 2px;
    background: linear-gradient(180deg, var(--color-primary) 0%, rgba(0, 220, 130, 0.1) 100%);
}

.timeline-item {
    display: flex;
    gap: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
    position: relative;
}

.timeline-item:last-child {
    margin-bottom: 0;
}

.timeline-number {
    flex-shrink: 0;
    width: 60px;
    height: 60px;
    background: var(--color-bg-primary);
    border: 2px solid var(--color-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: var(--font-size-lg);
    font-weight: 800;
    color: var(--color-primary);
    box-shadow: var(--shadow-glow);
    z-index: 1;
}

.timeline-content {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-md);
    flex: 1;
    transition: var(--transition-normal);
}

.timeline-item:hover .timeline-content {
    transform: translateX(10px);
    border-color: var(--color-primary);
    box-shadow: var(--shadow-md);
}

.timeline-content h3 {
    margin-bottom: var(--spacing-sm);
    color: var(--color-text-primary);
}

.timeline-content p {
    color: var(--color-text-secondary);
    margin: 0;
}
</style>
