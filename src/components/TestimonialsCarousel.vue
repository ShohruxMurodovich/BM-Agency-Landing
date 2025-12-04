<script setup>
import { Quote, Star } from 'lucide-vue-next'

const testimonials = [
  {
    name: 'Алишер Усманов',
    role: 'CEO, TechStore',
    content: 'С BM Agency мы выросли в 3 раза за полгода. Профессиональный подход к аналитике и рекламе дал невероятный результат.',
    rating: 5
  },
  {
    name: 'Мадина Каримова',
    role: 'Основатель, Beauty Shop',
    content: 'Команда полностью взяла на себя операционку. Теперь я занимаюсь развитием бренда, а продажи растут сами.',
    rating: 5
  },
  {
    name: 'Джамшид Рахимов',
    role: 'Директор, Home Goods',
    content: 'Отличная логистика и работа с контентом. Карточки товаров выглядят лучше, чем у конкурентов. Рекомендую!',
    rating: 5
  }
]
</script>

<template>
  <section class="testimonials" id="testimonials">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Отзывы клиентов</h2>
        <p class="section-subtitle">Истории успеха тех, кто нам доверяет</p>
      </div>

      <div class="testimonials-grid">
        <div v-for="(review, index) in testimonials" :key="index" class="testimonial-card">
          <div class="quote-icon">
            <Quote size="32" />
          </div>
          <p class="review-content">{{ review.content }}</p>
          
          <div class="review-footer">
            <div class="review-author">
              <div class="author-avatar">
                {{ review.name.charAt(0) }}
              </div>
              <div class="author-info">
                <h4>{{ review.name }}</h4>
                <span>{{ review.role }}</span>
              </div>
            </div>
            <div class="review-rating">
              <Star v-for="n in review.rating" :key="n" size="16" fill="currentColor" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-secondary);
}

.testimonials-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-md);
}

.testimonial-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    position: relative;
    transition: var(--transition-normal);
}

.testimonial-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-border-hover);
    box-shadow: var(--shadow-md);
}

.quote-icon {
    color: var(--color-primary);
    opacity: 0.2;
    margin-bottom: var(--spacing-md);
}

.review-content {
    font-size: var(--font-size-md);
    line-height: 1.6;
    margin-bottom: var(--spacing-lg);
    font-style: italic;
}

.review-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid var(--color-border);
    padding-top: var(--spacing-md);
}

.review-author {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.author-avatar {
    width: 48px;
    height: 48px;
    background: var(--color-gradient);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: var(--font-size-lg);
    color: var(--color-text-primary);
}

.author-info h4 {
    margin: 0;
    font-size: var(--font-size-sm);
}

.author-info span {
    font-size: var(--font-size-xs);
    color: var(--color-text-secondary);
}

.review-rating {
    display: flex;
    gap: 2px;
    color: #F59E0B;
}
</style>
