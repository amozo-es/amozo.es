# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website/portfolio for Alejandro Mozo, built with Astro 5.7.13 and Tailwind CSS v4.1.7. The site features a professional portfolio layout with a sidebar contact section, timeline sections for education and experience, and supports dark/light theme switching.

## Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Technology Stack

- **Astro 5.7.13**: Modern static site generator with component islands
- **Tailwind CSS v4.1.7**: CSS-first styling approach with custom design tokens
- **TypeScript**: Strict TypeScript configuration
- **Dark/Light Theme**: Custom theme implementation with localStorage persistence

## Key Architecture Notes

### Styling System
- Uses Tailwind CSS v4's CSS-first approach (styles are defined in `src/styles/global.css`, not `tailwind.config.js`)
- Custom color design tokens in CSS custom properties for both light and dark modes
- Smooth theme transitions with `transition-colors duration-300`
- Emerald/green accent color scheme with purple accents

### Component Structure
- **Layout Components**: `Layout.astro` (main layout), `Header.astro`, `Footer.astro`
- **Content Components**: `TimelineSection.astro`, `TimelineItem.astro`, `TechStackSection.astro`
- **UI Components**: `ThemeToggle.astro`, `ContactSidebar.astro`, `TechItem.astro`
- Fixed sidebar layout that becomes responsive on mobile

### Theme Implementation
- Theme detection logic in `Layout.astro` head section
- Checks localStorage first, then system preference
- Uses `class` strategy for dark mode (Tailwind config: `darkMode: 'class'`)
- Theme toggle component for user switching

### Project Organization
- Main page content in `src/pages/index.astro` with placeholder education/experience data
- Timeline sections support custom accent colors via props
- Sidebar contains contact information and social links
- Global CSS includes custom animations (fadeIn, slideUp, float) and glass effects

## Important Styling Notes

- Tailwind v4 requires CSS imports in `global.css` rather than relying on config file
- Custom color variables are defined as CSS custom properties and mapped to Tailwind via `@theme inline`
- The design uses oklch color space for better accessibility and perceptual uniformity
- Sidebar layout requires margin adjustments (`md:ml-64 lg:ml-72`) to prevent content overlap