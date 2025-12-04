<script setup>
import { Store, BarChart3, Truck, Code2 } from 'lucide-vue-next'

const services = [
  {
    icon: Store,
    title: 'Полное управление',
    shortDescription: 'Регистрация, карточки, SEO, отзывы',
    items: [
      {
        subtitle: 'Регистрация кабинета',
        description: 'Мы создаём и настраиваем ваш личный кабинет на маркетплейсе: заполняем все необходимые данные о компании, подключаем способы оплаты, настраиваем права доступа и интеграции. Гарантируем корректную подготовку профиля для начала продаж без ошибок и блокировок.'
      },
      {
        subtitle: 'Создание карточек',
        description: 'Формируем профессиональные карточки товаров: фото, описания, характеристики, SEO-теги, структура контента. Каждая карточка адаптирована под требования конкретного маркетплейса и построена так, чтобы повышать конверсию и привлекать покупателей.'
      },
      {
        subtitle: 'SEO оптимизация',
        description: 'Оптимизируем карточки по ключевым словам, улучшаем видимость товаров в поиске маркетплейса. Работаем с метаданными, релевантностью запроса, структурой контента и повышением позиции товара внутри категории.'
      },
      {
        subtitle: 'Работа с отзывами',
        description: 'Отслеживаем отзывы, анализируем обратную связь, оперативно реагируем на негатив, усиливаем положительное восприятие бренда. Формируем стратегию повышения рейтинга товаров и удержания лояльных клиентов.'
      }
    ]
  },
  {
    icon: BarChart3,
    title: 'Продвижение и реклама',
    shortDescription: 'Внутренняя и внешняя реклама',
    items: [
      {
        subtitle: 'Внутренняя реклама',
        description: 'Мы настраиваем рекламные кампании внутри маркетплейсов: карточные промо, продвижение в поиске, позиционирование в категориях. Оптимизируем ставки, анализируем эффективность и увеличиваем видимость товаров.'
      },
      {
        subtitle: 'Внешний трафик',
        description: 'Привлекаем покупателей из социальных сетей, контекстной рекламы и других внешних источников. Создаём рекламные креативы, настраиваем таргетинг и формируем стратегию, которая приводит дополнительный поток клиентов.'
      },
      {
        subtitle: 'Участие в акциях',
        description: 'Подбираем выгодные акции маркетплейсов, оформляем участие и контролируем условия. Анализируем влияние акций на продажи и выбираем оптимальную стратегию для роста оборотов без лишних затрат.'
      },
      {
        subtitle: 'Аналитика продаж',
        description: 'Предоставляем подробный анализ продаж: динамика, маржинальность, эффективность рекламных каналов, лучшие и слабые товары. Помогаем принимать решения на основе данных, а не интуиции.'
      }
    ]
  },
  {
    icon: Truck,
    title: 'Логистика и склад',
    shortDescription: 'Приёмка, упаковка, отгрузка',
    items: [
      {
        subtitle: 'Приёмка товара',
        description: 'Организуем правильную приёмку товара на складе: проверку количества, состояния, соответствия маркировке и документооборот. Гарантируем отсутствие ошибок перед дальнейшей отправкой.'
      },
      {
        subtitle: 'Упаковка и маркировка',
        description: 'Готовим товар к продаже: профессиональная упаковка, штрихкоды, маркировка, подготовка комплектов. Всё соответствует стандартам маркетплейсов и снижает риск возвратов.'
      },
      {
        subtitle: 'Отгрузка на МП',
        description: 'Берём на себя весь процесс отправки: создание поставок, оформление коробов, сдача на склад маркетплейса или курьеру. Обеспечиваем своевременные отгрузки для стабильных продаж.'
      },
      {
        subtitle: 'Работа с возвратами',
        description: 'Контролируем возвраты, проверяем состояние товара, анализируем причины и помогаем сократить процент возвратов. Грамотная обработка снижает убытки и сохраняет рейтинг продавца.'
      }
    ]
  },
  {
    icon: Code2,
    title: 'IT-Разработка',
    shortDescription: 'Сайты, боты, интеграции',
    items: [
      {
        subtitle: 'Интернет-магазины',
        description: 'Разрабатываем современные, быстрые и удобные сайты для e-commerce. Настраиваем каталог, корзину, оплату, личный кабинет и админ-панель, интегрируем CRM и складские сервисы.'
      },
      {
        subtitle: 'Telegram-боты',
        description: 'Создаём Telegram-ботов для автоматизации продаж, клиентской поддержки, оформления заказов и внутренних процессов. Разрабатываем индивидуальную логику и дизайн интерфейса.'
      },
      {
        subtitle: 'Интеграции',
        description: 'Настраиваем обмен данными между маркетплейсами, CRM, складами, 1С, ERP и другими системами. Автоматизация процессов снижает количество ошибок и ускоряет работу компании.'
      },
      {
        subtitle: 'Техническая поддержка',
        description: 'Обеспечиваем сопровождение проектов: обновления, мониторинг, устранение проблем, улучшения по запросу клиента. Работаем оперативно и держим ваши сервисы в стабильном состоянии.'
      }
    ]
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

      <div class="services-container">
        <div v-for="(service, index) in services" :key="index" class="service-card">
          <div class="service-header">
            <div class="service-icon-wrapper">
              <component :is="service.icon" size="32" />
            </div>
            <h3 class="service-title">{{ service.title }}</h3>
            <p class="service-short">{{ service.shortDescription }}</p>
          </div>
          
          <!-- Short feature list (always visible) -->
          <ul class="service-features-short">
            <li v-for="(item, iIndex) in service.items" :key="iIndex">
              <div class="check-dot"></div>
              {{ item.subtitle }}
            </li>
          </ul>
          
          <!-- Detailed content (visible on hover) -->
          <div class="service-content">
            <div v-for="(item, iIndex) in service.items" :key="iIndex" class="service-item">
              <h4 class="item-subtitle">{{ item.subtitle }}</h4>
              <p class="item-description">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-secondary);
}

.services-container {
    display: flex;
    gap: var(--spacing-sm);
    height: 600px;
    max-width: 1400px;
    margin: 0 auto;
}

.service-card {
    flex: 1;
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    cursor: pointer;
    display: flex;
    flex-direction: column;
}

.service-card:hover {
    flex: 3;
    border-color: var(--color-primary);
    box-shadow: var(--shadow-glow);
}

/* При hover на одной карточке, остальные сужаются */
.services-container:has(.service-card:hover) .service-card:not(:hover) {
    flex: 0.5;
    opacity: 0.5;
}

.services-container:has(.service-card:hover) .service-card:not(:hover) .service-header {
    align-items: center;
    justify-content: center;
    height: 100%;
}

.services-container:has(.service-card:hover) .service-card:not(:hover) .service-icon-wrapper {
    margin-bottom: var(--spacing-lg);
}

.services-container:has(.service-card:hover) .service-card:not(:hover) .service-title {
    writing-mode: vertical-rl;
    text-orientation: mixed;
    margin: 0;
    white-space: nowrap;
}

.services-container:has(.service-card:hover) .service-card:not(:hover) .service-short,
.services-container:has(.service-card:hover) .service-card:not(:hover) .service-features-short {
    display: none;
}

.service-header {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-bottom: var(--spacing-md);
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

.service-icon-wrapper {
    width: 64px;
    height: 64px;
    background: rgba(139, 92, 246, 0.1);
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
    transform: scale(1.1);
}

.service-title {
    font-size: var(--font-size-lg);
    margin-bottom: var(--spacing-sm);
    color: var(--color-text-primary);
}

.service-short {
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-md);
    transition: opacity 0.3s ease;
}

.service-card:hover .service-short {
    opacity: 0;
    max-height: 0;
}

.service-features-short {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    transition: all 0.3s ease;
}

.service-card:hover .service-features-short {
    opacity: 0;
    max-height: 0;
    overflow: hidden;
}

.service-features-short li {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
}

.check-dot {
    width: 6px;
    height: 6px;
    background: var(--color-primary);
    border-radius: 50%;
    flex-shrink: 0;
}

.service-content {
    opacity: 0;
    max-height: 0;
    overflow: hidden;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    display: flex;
    flex-direction: column;
    gap: var(--spacing-md);
}

.service-card:hover .service-content {
    opacity: 1;
    max-height: 500px;
    overflow-y: auto;
    padding-right: 10px;
}

/* Scrollbar styling */
.service-content::-webkit-scrollbar {
    width: 6px;
}

.service-content::-webkit-scrollbar-track {
    background: rgba(255, 255, 255, 0.05);
    border-radius: 10px;
}

.service-content::-webkit-scrollbar-thumb {
    background: var(--color-primary);
    border-radius: 10px;
}

.service-content::-webkit-scrollbar-thumb:hover {
    background: var(--color-primary-light);
}

.service-item {
    padding-bottom: var(--spacing-md);
    border-bottom: 1px solid var(--color-border);
}

.service-item:last-child {
    border-bottom: none;
    padding-bottom: 0;
}

.item-subtitle {
    font-size: var(--font-size-md);
    color: var(--color-primary);
    margin-bottom: 0.5rem;
    font-weight: 600;
}

.item-description {
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
    line-height: 1.6;
    margin: 0;
}

/* Responsive */
@media (max-width: 1024px) {
    .services-container {
        flex-direction: column;
        height: auto;
    }
    
    .service-card {
        flex: 1 !important;
        min-height: 200px;
    }
    
    .service-card:hover {
        flex: 1 !important;
    }
    
    .services-container:has(.service-card:hover) .service-card:not(:hover) {
        flex: 1 !important;
    }
}
</style>
