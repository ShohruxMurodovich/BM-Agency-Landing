<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-column">
          <div class="footer-logo">
            <img src="/logo.png" alt="BM Agency" />
          </div>
          <p class="footer-description">
            Первое и ведущее e-commerce агентство в Центральной Азии. Мы помогаем бизнесу расти на маркетплейсах.
          </p>
        </div>
        
        <div class="footer-column">
          <h4>Навигация</h4>
          <ul class="footer-links">
            <li><a href="#about">О нас</a></li>
            <li><a href="#analytics">Аналитика</a></li>
            <li><a href="#services">Услуги</a></li>
            <li><a href="#cases">Кейсы</a></li>
          </ul>
        </div>

        <div class="footer-column">
          <h4>Контакты</h4>
          <ul class="footer-links">
            <li><a href="https://t.me/bmagency_admin">Telegram</a></li>
            <li><a href="https://www.instagram.com/bmagency_e.commerce/">Instagram</a></li>
            <li><a href="mailto:bmagencyuz@gmail.com">Email</a></li>
          </ul>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; 2024 BM Agency. Все права защищены.</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
    background: var(--color-bg-primary);
    padding: var(--spacing-xl) 0 var(--spacing-md);
    border-top: 1px solid var(--color-border);
}

.footer-content {
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr;
    gap: var(--spacing-xl);
    margin-bottom: var(--spacing-xl);
}

.footer-logo img {
    height: 50px;
    margin-bottom: var(--spacing-md);
}

.footer-description {
    color: var(--color-text-secondary);
    max-width: 300px;
}

.footer-column h4 {
    color: var(--color-text-primary);
    margin-bottom: var(--spacing-md);
}

.footer-links {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
}

.footer-links a {
    color: var(--color-text-secondary);
    transition: var(--transition-fast);
}

.footer-links a:hover {
    color: var(--color-primary);
}

.footer-bottom {
    text-align: center;
    padding-top: var(--spacing-md);
    border-top: 1px solid var(--color-border);
    color: var(--color-text-tertiary);
    font-size: var(--font-size-sm);
}

@media (max-width: 768px) {
    .footer-content {
        grid-template-columns: 1fr;
        gap: var(--spacing-lg);
    }
}
</style>
