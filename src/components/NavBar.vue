<script setup>
import { ref } from 'vue'
import { Menu, X } from 'lucide-vue-next'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <div class="nav-content">
        <div class="logo">
          <img src="/logo.png" alt="BM Agency" />
        </div>
        
        <ul class="nav-links" :class="{ active: isMenuOpen }">
          <li><a href="#about" @click="closeMenu">О нас</a></li>
          <li><a href="#analytics" @click="closeMenu">Аналитика</a></li>
          <li><a href="#pricing" @click="closeMenu">Тарифы</a></li>
          <li><a href="#cases" @click="closeMenu">Кейсы</a></li>
          <li><a href="#contact" class="btn-primary" @click="closeMenu">Связаться</a></li>
        </ul>

        <button class="mobile-menu-btn" @click="toggleMenu">
          <Menu v-if="!isMenuOpen" />
          <X v-else />
        </button>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    background: var(--glass-bg);
    backdrop-filter: var(--glass-backdrop);
    border-bottom: 1px solid var(--glass-border);
    padding: var(--spacing-sm) 0;
    transition: all var(--transition-normal);
}

.nav-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo img {
    height: 55px;
    width: auto;
}

.nav-links {
    display: flex;
    gap: var(--spacing-md);
    align-items: center;
}

.nav-links a {
    font-weight: 500;
    font-size: var(--font-size-sm);
    color: var(--color-text-secondary);
    transition: var(--transition-fast);
}

.nav-links a:hover {
    color: var(--color-primary);
}

.nav-links .btn-primary {
    color: var(--color-bg-primary);
    background: var(--color-primary);
    padding: 0.5rem 1.5rem;
    border-radius: var(--radius-sm);
    font-weight: 600;
}

.nav-links .btn-primary:hover {
    background: var(--color-primary-light);
    color: var(--color-bg-primary);
    box-shadow: var(--shadow-glow);
}

.mobile-menu-btn {
    display: none;
    background: none;
    border: none;
    color: var(--color-text-primary);
    cursor: pointer;
    padding: 0.5rem;
}

@media (max-width: 768px) {
    .mobile-menu-btn {
        display: block;
    }

    .nav-links {
        position: fixed;
        top: 70px;
        left: 0;
        width: 100%;
        background: var(--color-bg-secondary);
        flex-direction: column;
        padding: var(--spacing-md);
        gap: var(--spacing-md);
        transform: translateY(-150%);
        transition: transform var(--transition-normal);
        border-bottom: 1px solid var(--color-border);
    }

    .nav-links.active {
        transform: translateY(0);
        box-shadow: var(--shadow-lg);
    }
}
</style>
