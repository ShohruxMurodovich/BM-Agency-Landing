# BM Agency - Premium E-commerce Landing Page

A modern, premium landing page for BM Agency - the leading e-commerce agency in Central Asia. Built with Vue 3, Vite, and featuring stunning dark purple & violet design with advanced data visualization.

![BM Agency](./public/logo.png)

## ✨ Features

### 🎨 Premium Design
- **Dark Purple & Violet Theme** - Modern, eye-catching color palette
- **Glassmorphism Effects** - Smooth, translucent UI elements
- **Micro-animations** - Engaging hover effects and smooth transitions
- **Fully Responsive** - Optimized for all screen sizes

### 📊 Data Visualization
- **Interactive Charts** - Real-time analytics using Chart.js
- **Revenue Growth Tracking** - Visual representation of client success
- **Order Analytics** - Comprehensive business metrics
- **Case Study Showcases** - Animated growth indicators

### 🚀 Key Sections
- **Hero Section** - Eye-catching introduction with key statistics
- **Analytics Dashboard** - Live data visualization
- **Services Grid** - Complete service offerings
- **Process Timeline** - Step-by-step workflow
- **Pricing Plans** - Three flexible tariff options
- **Success Cases** - Client success stories with metrics
- **FAQ** - Interactive accordion for common questions
- **Contact** - Direct Telegram, Instagram, and Email integration

### 📱 Contact Integration
- **Telegram** - Direct messaging with pre-filled templates
- **Instagram** - Social media connection
- **Email** - Professional communication channel

## 🛠️ Tech Stack

- **Vue 3** - Progressive JavaScript framework
- **Vite** - Next-generation frontend tooling
- **Chart.js** - Beautiful, responsive charts
- **vue-chartjs** - Vue wrapper for Chart.js
- **Lucide Icons** - Clean, consistent iconography
- **CSS Variables** - Dynamic theming system

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/ShohruxMurodovich/BM-Agency-Landing.git

# Navigate to project directory
cd BM-Agency-Landing

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🎯 Project Structure

```
BM-Agency-Landing/
├── public/
│   └── logo.png
├── src/
│   ├── components/
│   │   ├── NavBar.vue
│   │   ├── HeroSection.vue
│   │   ├── AnalyticsDashboard.vue
│   │   ├── ServicesGrid.vue
│   │   ├── ProcessTimeline.vue
│   │   ├── PricingSection.vue
│   │   ├── AdvantagesSection.vue
│   │   ├── CasesSection.vue
│   │   ├── FAQSection.vue
│   │   ├── ContactSection.vue
│   │   └── FooterSection.vue
│   ├── App.vue
│   ├── main.js
│   └── style.css
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

## 🎨 Color Palette

```css
Primary: #8B5CF6 (Vivid Violet)
Accent: #EC4899 (Pink)
Background: #0B0A14 (Deep Black-Purple)
Secondary BG: #13111C (Rich Dark Purple)
Tertiary BG: #1C1A29 (Lighter Purple)
Text: #FFFFFF (White)
Secondary Text: #9CA3AF (Cool Grey)
```

## 🌟 Key Features Breakdown

### Analytics Dashboard
- Revenue growth visualization
- Order volume tracking
- Key performance indicators
- Interactive hover tooltips

### Pricing Plans
- **Подключ** - Quick start package
- **BM Flow** (Popular) - 7.8% from revenue
- **BM Profit** - Partnership model (33.3% from net profit)

### Contact Methods
- **Telegram**: [@bmagency_admin](https://t.me/bmagency_admin)
- **Instagram**: [@bmagency_e.commerce](https://www.instagram.com/bmagency_e.commerce/)
- **Email**: bmagencyuz@gmail.com

## 🚀 Performance

- Fast page loads with Vite
- Optimized bundle size
- Lazy-loaded components
- Smooth scroll animations
- Intersection Observer for on-scroll effects

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 🚀 Deployment (VPS / Nginx)

If you are deploying to a VPS (like PSCloud), follow these steps:

1.  **Build the project** on your local machine or server:
    ```bash
    npm run build
    ```
    This will create a `dist` folder.

2.  **Configure Nginx**:
    Copy the provided `nginx.conf` or use its content for your site configuration.
    
    *Key Nginx settings for Vue SPA:*
    - Root directory should point to `/dist` folder.
    - `try_files $uri $uri/ /index.html;` is required to prevent 404s on page refresh.

3.  **Restart Nginx**:
    ```bash
    sudo systemctl restart nginx
    ```

## 🤝 Contributing

This is a private project for BM Agency. For inquiries, please contact via the methods listed above.

## 📄 License

Copyright © 2024 BM Agency. All rights reserved.

## 📞 Contact

- **Website**: [BM Agency Landing](https://github.com/ShohruxMurodovich/BM-Agency-Landing)
- **Telegram**: [@bmagency_admin](https://t.me/bmagency_admin)
- **Instagram**: [@bmagency_e.commerce](https://www.instagram.com/bmagency_e.commerce/)
- **Email**: bmagencyuz@gmail.com

---

Made with ❤️ by BM Agency - Leading E-commerce Agency in Central Asia
