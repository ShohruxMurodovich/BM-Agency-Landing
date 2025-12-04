<script setup>
import { Send, Mail, Instagram } from 'lucide-vue-next'
</script>

<template>
  <section class="contact" id="contact">
    <div class="container">
      <div class="contact-content">
        <div class="contact-info">
          <h2 class="section-title">Готовы начать?</h2>
          <p class="section-subtitle">Оставьте заявку, и мы проведем бесплатный аудит вашего бизнеса</p>
          
          <div class="contact-methods">
            <a href="https://t.me/bmagency_admin" class="contact-btn telegram-btn" target="_blank">
              <div class="btn-icon">
                <Send size="24" />
              </div>
              <div class="btn-text">
                <span class="btn-label">Telegram</span>
                <span class="btn-sublabel">@bmagency_admin</span>
              </div>
            </a>
            
            <a href="https://www.instagram.com/bmagency_e.commerce/" class="contact-btn instagram-btn" target="_blank">
              <div class="btn-icon">
                <Instagram size="24" />
              </div>
              <div class="btn-text">
                <span class="btn-label">Instagram</span>
                <span class="btn-sublabel">bmagency_e.commerce</span>
              </div>
            </a>
            
            <a href="mailto:bmagencyuz@gmail.com" class="contact-btn email-btn">
              <div class="btn-icon">
                <Mail size="24" />
              </div>
              <div class="btn-text">
                <span class="btn-label">Email</span>
                <span class="btn-sublabel">bmagencyuz@gmail.com</span>
              </div>
            </a>
          </div>
        </div>

        <div class="contact-cta-wrapper">
          <div class="cta-card">
            <h3>Хотите получить бесплатный аудит?</h3>
            <p>Нажмите на кнопку ниже, и мы автоматически сформируем заявку в Telegram</p>
            
            <a href="https://t.me/bmagency_admin?text=Здравствуйте! Хочу получить бесплатный аудит моего бизнеса." class="btn-primary btn-audit full-width" target="_blank">
              <Send size="20" />
              <span>Получить бесплатный аудит</span>
            </a>
            
            <p class="form-note">
              Откроется приложение Telegram с готовым сообщением
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
    padding: var(--spacing-xl) 0;
    background: var(--color-bg-secondary);
}

.contact-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--spacing-xl);
    max-width: 1000px; /* Reduced max-width for tighter layout */
    margin: 0 auto;
    align-items: start;
}

.contact-info h2 {
    margin-bottom: var(--spacing-sm);
}

.contact-info p {
    margin-bottom: var(--spacing-lg);
    font-size: var(--font-size-lg);
}

.contact-methods {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-sm); /* Reduced gap */
}

.contact-btn {
    display: flex;
    align-items: center;
    gap: var(--spacing-md);
    padding: 1rem; /* Reduced padding */
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    transition: all var(--transition-normal);
}

.contact-btn:hover {
    transform: translateX(10px);
    border-color: var(--color-primary);
    background: var(--color-bg-primary);
    box-shadow: var(--shadow-glow);
}

.btn-icon {
    width: 48px; /* Reduced size */
    height: 48px; /* Reduced size */
    background: rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--color-text-primary);
    transition: var(--transition-normal);
}

.contact-btn:hover .btn-icon {
    background: var(--color-primary);
    color: var(--color-bg-primary);
}

.btn-text {
    display: flex;
    flex-direction: column;
    gap: 0.1rem;
}

.btn-label {
    font-weight: 700;
    font-size: var(--font-size-md); /* Reduced font size */
    color: var(--color-text-primary);
}

.btn-sublabel {
    font-size: var(--font-size-sm); /* Reduced font size */
    color: var(--color-text-secondary);
}

.contact-cta-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
}

.cta-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-lg);
    box-shadow: var(--shadow-lg);
    text-align: center;
    width: 100%;
    max-width: 500px;
}

.cta-card h3 {
    font-size: var(--font-size-xl);
    margin-bottom: var(--spacing-sm);
}

.cta-card p {
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-md);
}

.full-width {
    width: 100%;
    justify-content: center;
    margin-bottom: var(--spacing-sm);
}

.btn-audit {
    padding: 0.875rem 1.5rem;
    font-size: var(--font-size-sm);
    gap: 0.5rem;
    align-items: center;
    white-space: nowrap;
    display: flex;
}

.btn-audit svg {
    flex-shrink: 0;
}

.btn-audit span {
    line-height: 1;
}

.form-note {
    font-size: var(--font-size-xs);
    color: var(--color-text-tertiary);
    margin: 0;
}

@media (max-width: 768px) {
    .contact-content {
        grid-template-columns: 1fr;
        gap: var(--spacing-lg);
    }
}
</style>
