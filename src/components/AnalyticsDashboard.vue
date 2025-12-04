<script setup>
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  BarElement,
  Title,
  Tooltip,
  Legend,
  Filler
} from 'chart.js'
import { Line, Bar } from 'vue-chartjs'
import { ref } from 'vue'
import { TrendingUp, Users, ShoppingBag, DollarSign } from 'lucide-vue-next'

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  BarElement,
  Title,
  Tooltip,
  Legend,
  Filler
)

const chartOptions = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      display: false
    },
    tooltip: {
      backgroundColor: 'rgba(2, 4, 32, 0.9)',
      titleColor: '#fff',
      bodyColor: '#94A3B8',
      borderColor: 'rgba(255, 255, 255, 0.1)',
      borderWidth: 1,
      padding: 10,
      displayColors: false
    }
  },
  scales: {
    x: {
      grid: {
        color: 'rgba(255, 255, 255, 0.05)'
      },
      ticks: {
        color: '#64748B'
      }
    },
    y: {
      grid: {
        color: 'rgba(255, 255, 255, 0.05)'
      },
      ticks: {
        color: '#64748B'
      }
    }
  }
}

const revenueData = {
  labels: ['Янв', 'Фев', 'Мар', 'Апр', 'Май', 'Июн'],
  datasets: [
    {
      label: 'Рост выручки',
      backgroundColor: (ctx) => {
        const canvas = ctx.chart.ctx;
        const gradient = canvas.createLinearGradient(0, 0, 0, 400);
        gradient.addColorStop(0, 'rgba(0, 220, 130, 0.5)');
        gradient.addColorStop(1, 'rgba(0, 220, 130, 0)');
        return gradient;
      },
      borderColor: '#00DC82',
      borderWidth: 2,
      pointBackgroundColor: '#00DC82',
      pointBorderColor: '#fff',
      pointHoverBackgroundColor: '#fff',
      pointHoverBorderColor: '#00DC82',
      fill: true,
      tension: 0.4,
      data: [1200000, 1900000, 2500000, 3200000, 4800000, 6500000]
    }
  ]
}

const ordersData = {
  labels: ['Янв', 'Фев', 'Мар', 'Апр', 'Май', 'Июн'],
  datasets: [
    {
      label: 'Заказы',
      backgroundColor: '#3B82F6',
      borderRadius: 4,
      data: [150, 230, 380, 490, 650, 890]
    }
  ]
}

const stats = [
  {
    label: 'Средний рост продаж',
    value: '+340%',
    icon: TrendingUp,
    color: '#00DC82'
  },
  {
    label: 'ROI клиентов',
    value: '450%',
    icon: DollarSign,
    color: '#3B82F6'
  },
  {
    label: 'Заказов обработано',
    value: '50k+',
    icon: ShoppingBag,
    color: '#F59E0B'
  },
  {
    label: 'Удержание клиентов',
    value: '98%',
    icon: Users,
    color: '#EC4899'
  }
]
</script>

<template>
  <section class="analytics" id="analytics">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Результаты в цифрах</h2>
        <p class="section-subtitle">Прозрачная аналитика и реальный рост вашего бизнеса</p>
      </div>

      <div class="stats-grid">
        <div v-for="(stat, index) in stats" :key="index" class="stat-card">
          <div class="stat-icon" :style="{ color: stat.color, background: `${stat.color}15` }">
            <component :is="stat.icon" size="24" />
          </div>
          <div class="stat-content">
            <div class="stat-value" :style="{ color: stat.color }">{{ stat.value }}</div>
            <div class="stat-label">{{ stat.label }}</div>
          </div>
        </div>
      </div>

      <div class="charts-grid">
        <div class="chart-card">
          <div class="chart-header">
            <h3>Динамика выручки</h3>
            <span class="chart-badge">+441%</span>
          </div>
          <div class="chart-container">
            <Line :data="revenueData" :options="chartOptions" />
          </div>
        </div>

        <div class="chart-card">
          <div class="chart-header">
            <h3>Рост количества заказов</h3>
            <span class="chart-badge blue">+280%</span>
          </div>
          <div class="chart-container">
            <Bar :data="ordersData" :options="chartOptions" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.analytics {
    background: var(--color-bg-secondary);
    padding: var(--spacing-xl) 0;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
}

.stat-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-md);
    display: flex;
    align-items: center;
    gap: var(--spacing-md);
    transition: var(--transition-normal);
}

.stat-card:hover {
    transform: translateY(-5px);
    border-color: var(--color-border-hover);
    box-shadow: var(--shadow-md);
}

.stat-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.stat-value {
    font-size: var(--font-size-xl);
    font-weight: 700;
    line-height: 1;
    margin-bottom: 0.25rem;
    background: none;
    -webkit-text-fill-color: initial;
}

.stat-label {
    color: var(--color-text-secondary);
    font-size: var(--font-size-sm);
}

.charts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: var(--spacing-md);
}

.chart-card {
    background: var(--color-bg-tertiary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--spacing-md);
}

.chart-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--spacing-md);
}

.chart-header h3 {
    margin: 0;
    font-size: var(--font-size-md);
}

.chart-badge {
    background: rgba(0, 220, 130, 0.1);
    color: var(--color-primary);
    padding: 0.25rem 0.75rem;
    border-radius: 20px;
    font-size: var(--font-size-xs);
    font-weight: 600;
}

.chart-badge.blue {
    background: rgba(59, 130, 246, 0.1);
    color: var(--color-accent);
}

.chart-container {
    height: 300px;
    width: 100%;
}

@media (max-width: 768px) {
    .charts-grid {
        grid-template-columns: 1fr;
    }
}
</style>
