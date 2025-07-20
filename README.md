# Personal Portfolio Website

A modern, responsive portfolio website built with Svelte and Tailwind CSS, featuring smooth animations and a beautiful design.

## ✨ Features

- **Responsive Design**: Mobile-first approach ensuring great experience on all devices
- **Smooth Animations**: GSAP-powered scroll animations and Svelte transitions
- **Modern UI**: Clean design with gradients and professional styling
- **Interactive Sections**: Hero, About, Projects, and Contact sections
- **Performance Optimized**: Built with Vite for fast development and optimized builds

## 🛠️ Tech Stack

- **Frontend Framework**: [Svelte](https://svelte.dev/)
- **Build Tool**: [Vite](https://vitejs.dev/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Animations**: [GSAP](https://greensock.com/gsap/) + Svelte Transitions
- **Icons**: Unicode Emojis (easily replaceable)

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd profile
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and visit `http://localhost:5173`

## 📁 Project Structure

```
src/
├── lib/
│   ├── Hero.svelte          # Hero section with animated intro
│   ├── About.svelte         # About section with profile info
│   ├── Projects.svelte      # Projects showcase
│   ├── Contact.svelte       # Contact form and information
│   ├── Navigation.svelte    # Header navigation
│   └── Footer.svelte        # Footer component
├── App.svelte               # Main application component
├── app.css                  # Global styles with Tailwind
└── main.js                  # Application entry point
```

## 🎨 Customization

### Personal Information
Update the following files with your personal information:
- `src/lib/Hero.svelte` - Name and intro text
- `src/lib/About.svelte` - Profile description and skills
- `src/lib/Projects.svelte` - Your projects and portfolio items
- `src/lib/Contact.svelte` - Contact information and social links

### Styling
- `tailwind.config.js` - Customize colors, animations, and design tokens
- `src/app.css` - Global styles and custom CSS classes

### Images
Replace placeholder profile images and project screenshots:
- Add your profile image to `public/` directory
- Update image references in components

## 🎬 Animations

The website includes several types of animations:
- **GSAP ScrollTrigger**: Scroll-based animations for sections
- **Svelte Transitions**: Component entry/exit animations
- **CSS Animations**: Hover effects and micro-interactions
- **Custom Keyframes**: Defined in Tailwind config

## 📱 Responsive Design

The website is fully responsive with breakpoints:
- **Mobile**: `< 768px`
- **Tablet**: `768px - 1024px`
- **Desktop**: `> 1024px`

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

### Deploy
You can deploy the `dist` folder to any static hosting service:
- [Vercel](https://vercel.com/)
- [Netlify](https://netlify.com/)
- [GitHub Pages](https://pages.github.com/)
- [Firebase Hosting](https://firebase.google.com/docs/hosting)

## 🔧 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally

## 🎯 Performance

- Optimized bundle size with Vite
- Lazy loading for images
- Efficient CSS with Tailwind's purging
- GSAP optimizations for smooth 60fps animations

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Feel free to fork this project and customize it for your own portfolio!

---

Built with ❤️ using Svelte, Tailwind CSS, and GSAP
