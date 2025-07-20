<!-- Use this file to provide workspace-specific custom instructions to Copilot. For more details, visit https://code.visualstudio.com/docs/copilot/copilot-customization#_use-a-githubcopilotinstructionsmd-file -->

# Personal Portfolio Website - Copilot Instructions

This is a personal portfolio website built with Svelte and Tailwind CSS. The project features:

## Tech Stack
- **Frontend Framework**: Svelte with Vite
- **Styling**: Tailwind CSS with custom design system
- **Animations**: GSAP and Svelte transitions
- **Build Tool**: Vite

## Project Structure
- `src/App.svelte` - Main application component
- `src/lib/` - Reusable components (Hero, About, Projects, Contact, Navigation, Footer)
- `src/app.css` - Global styles with Tailwind CSS
- `tailwind.config.js` - Tailwind CSS configuration with custom animations

## Design Principles
- Mobile-first responsive design
- Smooth animations and transitions
- Modern gradient color scheme (blues and purples)
- Clean, professional layout
- Accessibility considerations

## Animation Guidelines
- Use GSAP for complex scroll-triggered animations
- Use Svelte transitions for component entry/exit animations
- Maintain consistent easing and timing
- Ensure animations don't interfere with accessibility

## Styling Conventions
- Use Tailwind CSS utility classes
- Custom components defined in CSS layers
- Consistent spacing with Tailwind's scale
- Responsive breakpoints: sm, md, lg, xl

When making changes:
1. Maintain the existing design system and color palette
2. Ensure all components remain responsive
3. Test animations for performance
4. Follow Svelte best practices for reactivity and component structure
