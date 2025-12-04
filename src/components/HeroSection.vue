<script setup>
import { ArrowRight, TrendingUp, ShieldCheck, Award } from 'lucide-vue-next'
</script>

<template>
  <section class="hero" id="hero">
    <div class="hero-bg"></div>
    <div class="container">
      <div class="hero-content">
        <div class="status-badge animate-in">
          <Award class="badge-icon" size="16" />
          <span>Первое и ведущее e-commerce агентство в Центральной Азии</span>
        </div>
        
        <h1 class="hero-title animate-in">
          BM Agency — <span class="gradient-text">работаем исключительно на результат</span>
        </h1>
        
        <p class="hero-subtitle animate-in">
          Полный цикл продаж на маркетплейсах. Мы гарантируем рост продаж и обеспечиваем профессиональное управление вашим бизнесом с оплатой за результат.
        </p>
        
        <div class="hero-features animate-in">
          <div class="hero-feature">
            <div class="feature-icon-wrapper">
              <TrendingUp size="20" />
            </div>
            <span>Гарантированный рост</span>
          </div>
          <div class="hero-feature">
            <div class="feature-icon-wrapper">
              <ShieldCheck size="20" />
            </div>
            <span>Уникальный опыт</span>
          </div>
          <div class="hero-feature">
            <div class="feature-icon-wrapper">
              <Award size="20" />
            </div>
            <span>Профессионализм</span>
          </div>
        </div>

        <div class="hero-cta animate-in">
          <a href="#contact" class="btn-primary btn-large">
            Получить аудит
            <ArrowRight size="20" />
          </a>
          <a href="#pricing" class="btn-secondary btn-large">Узнать тарифы</a>
        </div>
        
        <div class="hero-stats animate-in">
          <div class="stat-item">
            <div class="stat-number">5+</div>
            <div class="stat-label">лет опыта</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">5+</div>
            <div class="stat-label">маркетплейсов</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">1000+</div>
            <div class="stat-label">проектов</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">7.8%</div>
            <div class="stat-label">от оборота</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 180px;
    padding-bottom: var(--spacing-xl);
    overflow: hidden;
}

.hero-bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
        radial-gradient(circle at 15% 50%, rgba(139, 92, 246, 0.08) 0%, transparent 50%),
        radial-gradient(circle at 85% 30%, rgba(236, 72, 153, 0.08) 0%, transparent 50%);
    z-index: -1;
}

.hero-content {
    text-align: center;
    max-width: 1000px;
    margin: 0 auto;
}

.status-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(139, 92, 246, 0.1);
    border: 1px solid rgba(139, 92, 246, 0.2);
    padding: 0.5rem 1rem;
    border-radius: 50px;
    color: var(--color-primary);
    font-weight: 600;
    font-size: var(--font-size-sm);
    margin-bottom: var(--spacing-md);
    animation: fadeInUp 0.8s ease;
}

.hero-title {
    margin-bottom: var(--spacing-md);
    line-height: 1.1;
}

.hero-subtitle {
    font-size: clamp(1.1rem, 2vw, 1.25rem);
    color: var(--color-text-secondary);
    margin-bottom: var(--spacing-lg);
    line-height: 1.6;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    animation: fadeInUp 0.8s ease 0.2s both;
}

.hero-features {
    display: flex;
    justify-content: center;
    gap: var(--spacing-lg);
    margin-bottom: var(--spacing-lg);
    flex-wrap: wrap;
    animation: fadeInUp 0.8s ease 0.3s both;
}

.hero-feature {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    color: var(--color-text-primary);
    font-weight: 500;
}

.feature-icon-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    background: rgba(139, 92, 246, 0.1);
    border-radius: 50%;
    color: var(--color-primary);
}

.hero-cta {
    display: flex;
    gap: var(--spacing-md);
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: var(--spacing-xl);
    animation: fadeInUp 0.8s ease 0.4s both;
}

.btn-large {
    padding: 1rem 2rem;
    font-size: var(--font-size-md);
    border-radius: var(--radius-md);
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: all var(--transition-normal);
}

.btn-primary {
    background: var(--color-primary);
    color: var(--color-bg-primary);
}

.btn-primary:hover {
    background: var(--color-primary-light);
    transform: translateY(-2px);
    box-shadow: var(--shadow-glow);
}

.btn-secondary {
    background: rgba(255, 255, 255, 0.05);
    color: var(--color-text-primary);
    border: 1px solid var(--color-border);
}

.btn-secondary:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: var(--color-text-primary);
    transform: translateY(-2px);
}

.hero-stats {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: var(--spacing-md);
    padding: var(--spacing-md);
    background: var(--glass-bg);
    border: 1px solid var(--glass-border);
    border-radius: var(--radius-lg);
    backdrop-filter: var(--glass-backdrop);
    animation: fadeInUp 0.8s ease 0.5s both;
}

.stat-item {
    text-align: center;
}

.stat-number {
    font-size: var(--font-size-xl);
    font-weight: 800;
    margin-bottom: 0.25rem;
    color: #8B5CF6; /* Bright Purple explicitly */
    background: none;
    -webkit-text-fill-color: initial;
}

.stat-label {
    color: var(--color-text-secondary);
    font-size: var(--font-size-sm);
    font-weight: 500;
}

@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Ultra-compact mobile optimization (≤425px) */
@media (max-width: 425px) {
    .hero {
        padding: 5rem 0 3rem;
        min-height: auto;
    }

    .status-badge {
        display: none; /* Hide badge on very small screens */
    }

    .hero-title {
        font-size: 1.75rem;
        line-height: 1.3;
        margin-bottom: 1rem;
    }

    .hero-subtitle {
        font-size: 0.875rem;
        line-height: 1.5;
        margin-bottom: 1.25rem;
    }

    .hero-features {
        display: none; /* Hide features on very small screens to save space */
    }

    .hero-cta {
        gap: 0.75rem;
        margin-bottom: 1.5rem;
    }

    .btn-large {
        padding: 0.875rem 1.25rem;
        font-size: 0.875rem;
    }

    .hero-stats {
        padding: 1rem 0.75rem;
        gap: 0.75rem;
    }

    .stat-item {
        padding: 0.5rem;
    }

    .stat-number {
        font-size: 1.5rem;
        margin-bottom: 0.25rem;
    }

    .stat-label {
        font-size: 0.75rem;
    }
}
</style>
```
