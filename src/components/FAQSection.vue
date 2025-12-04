<script setup>
import { ref } from 'vue'
import { Plus, Minus } from 'lucide-vue-next'

const activeFaq = ref(null)

const toggleFaq = (index) => {
  activeFaq.value = activeFaq.value === index ? null : index
}

const faqs = [
  {
    question: 'Как работает модель оплаты 7.8%?',
    answer: 'Вы платите комиссию только с фактически проданных товаров. Мы не берем фиксированную плату за ведение кабинета в тарифе BM Flow. Это мотивирует нас работать на результат.'
  },
  {
    question: 'Когда я увижу первые продажи?',
    answer: 'Обычно первые продажи начинаются через 1-2 недели после запуска, когда товары поступают на склад и проходят модерацию. Мы делаем все возможное для быстрого старта.'
  },
  {
    question: 'С какими маркетплейсами вы работаете?',
    answer: 'Мы работаем с Uzum Market, Yandex Market, Wildberries, Ozon, Alif Shop и другими популярными площадками в СНГ.'
  },
  {
    question: 'Кто занимается возвратами?',
    answer: 'Мы полностью берем на себя работу с возвратами: забираем товар, проверяем его состояние и при необходимости переупаковываем для повторной продажи.'
  },
  {
    question: 'Нужно ли мне нанимать сотрудников?',
    answer: 'Нет, мы предоставляем полную команду: менеджера, контент-мейкера, маркетолога и логистов. Вам не нужно тратить время на найм и обучение.'
  }
]
</script>

<template>
  <section class="faq" id="faq">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Частые вопросы</h2>
        <p class="section-subtitle">Все, что нужно знать о сотрудничестве с нами</p>
      </div>

      <div class="faq-list">
        <div v-for="(item, index) in faqs" :key="index" 
             class="faq-item" :class="{ active: activeFaq === index }">
          <div class="faq-question" @click="toggleFaq(index)">
            <h3>{{ item.question }}</h3>
            <div class="faq-icon">
              <Minus v-if="activeFaq === index" size="20" />
              <Plus v-else size="20" />
            </div>
          </div>
          <div class="faq-answer">
            <p>{{ item.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-primary);
}

.faq-list {
    max-width: 800px;
    margin: 0 auto;
}

.faq-item {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    margin-bottom: var(--spacing-md);
    overflow: hidden;
    transition: all var(--transition-normal);
}

.faq-item:hover {
    border-color: var(--color-border-hover);
}

.faq-item.active {
    border-color: var(--color-primary);
    background: var(--color-bg-secondary);
}

.faq-question {
    padding: var(--spacing-md);
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: var(--spacing-md);
}

.faq-question h3 {
    margin: 0;
    font-size: var(--font-size-md);
    font-weight: 600;
    color: var(--color-text-primary);
}

.faq-icon {
    color: var(--color-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    background: rgba(0, 220, 130, 0.1);
    border-radius: 50%;
    transition: var(--transition-normal);
}

.faq-item.active .faq-icon {
    background: var(--color-primary);
    color: var(--color-bg-primary);
}

.faq-answer {
    max-height: 0;
    overflow: hidden;
    transition: max-height var(--transition-normal);
}

.faq-item.active .faq-answer {
    max-height: 200px;
}

.faq-answer p {
    padding: 0 var(--spacing-md) var(--spacing-md);
    color: var(--color-text-secondary);
    margin: 0;
    line-height: 1.6;
}
</style>
