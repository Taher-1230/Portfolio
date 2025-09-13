# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a **dynamic portfolio website** built as a single-page application using vanilla HTML5, CSS3, and JavaScript. The project emphasizes modern animations, theme switching, and responsive design without any frameworks.

Key characteristics:
- **Vanilla JavaScript**: No frameworks - pure ES6+ JavaScript for all functionality
- **CSS Variables & Custom Properties**: Extensive use for theming and responsive design  
- **Animation-Heavy**: Intersection Observer API, CSS transforms, and hardware acceleration
- **Theme Toggle**: Dark/light mode with localStorage persistence
- **Mobile-First**: Responsive design with hamburger navigation

## Development Commands

### Start Development Server
```powershell
npm run dev
```
Starts live-server on port 3000 with auto-reload. Best for active development.

### Alternative Server Options
```powershell
npm run serve
```
Starts http-server on port 8080 for testing production-like environment.

### Build & Optimization
```powershell
npm run build
```
Minifies CSS and JavaScript files for production deployment.

Individual build steps:
```powershell
npm run minify-css    # Minifies css/styles.css to css/styles.min.css
npm run minify-js     # Minifies js/script.js to js/script.min.js
```

### Code Quality
```powershell
npm run lint          # ESLint JavaScript files
npm run format        # Prettier formatting for HTML, CSS, JS
npm run validate      # HTML validation
```

### Quick Development Start
For immediate development without npm:
```powershell
# Simply open index.html in browser - no server required for basic functionality
start index.html
```

## Architecture & Code Structure

### File Organization
```
portfolio-website/
├── index.html          # Single-page HTML structure
├── css/
│   └── styles.css      # Monolithic stylesheet with CSS variables
├── js/
│   └── script.js       # All JavaScript functionality in one file
└── assets/             # Static assets (currently empty)
```

### CSS Architecture

**CSS Variables System**: The entire design system is built on CSS custom properties defined in `:root` and `[data-theme="dark"]`:

```css path=css/styles.css start=2
:root {
  --bg-primary: #ffffff;
  --accent-primary: #667eea;
  --accent-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  /* ... */
}
```

**Key Design Patterns**:
- **Glass morphism**: Navigation uses `backdrop-filter: blur(20px)`
- **Gradient accents**: All interactive elements use CSS gradients  
- **Hardware acceleration**: Transform-based animations with `will-change`
- **CSS Grid & Flexbox**: Layout system without any framework dependencies

### JavaScript Architecture

**Module Pattern**: All functionality is organized into initialization functions called from `DOMContentLoaded`:

```javascript path=js/script.js start=4
document.addEventListener('DOMContentLoaded', function() {
    initializeThemeToggle();
    initializeNavigation(); 
    initializeAnimations();
    initializeSkillBars();
    initializeCounters();
    initializeContactForm();
    initializeScrollEffects();
    initializeTechOrbit();
});
```

**Core Systems**:

1. **Theme System**: Uses `localStorage` + `data-theme` attribute
2. **Navigation**: Intersection Observer for active states + smooth scrolling
3. **Animation Engine**: Intersection Observer triggers CSS transforms
4. **Performance**: Throttled scroll events and GPU-accelerated animations

### Animation System

The animation system is built around the **Intersection Observer API** for performance:

- **Threshold-based triggering**: Elements animate when 10% visible
- **CSS Transform transitions**: Hardware-accelerated `translateY` and `opacity`
- **Staggered animations**: Different elements have different delays
- **Counter animations**: JavaScript-driven number counting with easing

### Theme Toggle Implementation

The theme system works through:
1. **CSS Variables**: All colors defined as custom properties
2. **Data Attributes**: `[data-theme="dark"]` selector overrides
3. **LocalStorage**: Persists user preference across sessions  
4. **Smooth Transitions**: 0.3s ease transitions on theme change

## Development Guidelines

### Working with Animations
- All animations use `transform` and `opacity` for 60fps performance
- Use `will-change` property sparingly and remove after animation
- Prefer CSS animations over JavaScript for simple transitions
- Test animations on lower-powered devices

### Theme Development
- Always define both light and dark variants for new CSS variables
- Use semantic variable names (`--text-primary` not `--color-gray-900`)  
- Test theme switching extensively - it's a core feature

### Adding New Sections
When adding content sections:
1. Add section with unique `id` to `index.html`
2. Add corresponding navigation link in nav menu
3. Update JavaScript navigation array in `initializeNavigation()`
4. Apply animation classes for Intersection Observer

### Performance Considerations
- **Throttle scroll events** - current implementation already optimized
- **Use CSS `contain` property** for heavy animation elements  
- **Minimize DOM queries** - cache selectors in module scope
- **Prefer event delegation** over multiple event listeners

### Asset Management  
- The `assets/` directory is currently empty - add images/icons here
- Consider using WebP format for images with fallbacks
- Optimize all assets before adding to maintain fast loading

## Browser Requirements

Target browsers (from package.json browserslist):
- \> 1% market share
- Last 2 versions
- Not dead browsers

Minimum versions for core features:
- **Intersection Observer**: Chrome 51+, Firefox 55+
- **CSS Custom Properties**: Chrome 49+, Firefox 31+  
- **CSS Grid**: Chrome 57+, Firefox 52+

## Local Development Notes

### Windows-Specific
- Use PowerShell for npm commands (current environment)
- Live-server works well with Windows Defender (no blocking issues)
- Consider using `npm run serve` if live-server has path issues

### Common Development Tasks
- **Testing animations**: Use browser dev tools Timeline to monitor performance
- **Theme debugging**: Use dev tools to toggle `data-theme` attribute  
- **Mobile testing**: Use responsive design mode + device simulation
- **Performance profiling**: Check for layout thrashing in animations

### Customization Points
Most common customization areas:
1. **Personal info**: Update name, title, contact details in `index.html`
2. **Color scheme**: Modify CSS variables in `:root` and `[data-theme="dark"]`
3. **Projects**: Replace placeholder projects in the Projects section
4. **Skills**: Update skill categories and progress percentages
5. **Animation timing**: Adjust CSS transition durations and delays

This codebase prioritizes visual impact and smooth animations over complex architecture - perfect for a portfolio that needs to make a strong first impression.