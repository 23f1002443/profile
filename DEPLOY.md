# GitHub Pages Deployment Guide

## Quick Deploy to GitHub Pages

Your portfolio is now ready to deploy! Follow these steps:

## Option 1: Deploy with GitHub Actions (Recommended)

1. **Create a new repository on GitHub:**
   - Go to [github.com/new](https://github.com/new)
   - Repository name: `profile` (or any name you prefer)
   - Make it public
   - Don't initialize with README (we already have one)

2. **Connect your local repo to GitHub:**
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/profile.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to your repository settings
   - Scroll down to "Pages" section
   - Source: "GitHub Actions"
   - The workflow will automatically deploy your site

4. **Your site will be live at:**
   `https://YOUR_USERNAME.github.io/profile/`

## Option 2: Manual Deploy

If you prefer manual deployment:

```bash
npm run deploy
```

This will build and push to the gh-pages branch.

## Local Development

- **Start dev server:** `npm run dev`
- **Build for production:** `npm run build`
- **Preview build:** `npm run preview`

## Customization

- Update personal info in `src/lib/` components
- Replace profile image in `public/monke-profile.png`
- Modify colors in `tailwind.config.js`
- Add your projects in `src/lib/Projects.svelte`

Your "rise of monke" portfolio is ready to share! 🐒✨
