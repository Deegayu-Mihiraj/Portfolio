# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a modern, responsive personal portfolio website for Deegayu Mihiraj, a BSc.Hons Information Systems student. Built with vanilla HTML, CSS, and JavaScript, focusing on performance, accessibility, and modern web standards.

**Portfolio Motto:** "Learning by building, growing by sharing 🌱"

## Common Commands

### Development Server
```bash
# Using Python (recommended)
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

### Open in Browser
After starting a local server:
```
http://localhost:8000
```

### Testing Across Devices
```bash
# Find your local IP for mobile testing
ipconfig | grep "IPv4 Address"

# Then access: http://[your-ip]:8000
```

## Architecture Overview

### File Structure
- **`index.html`** - Single-page application with semantic HTML5 structure
- **`css/style.css`** - Comprehensive styling with CSS variables and responsive design
- **`js/script.js`** - Interactive functionality and animations
- **`README.md`** - Detailed project documentation

### CSS Architecture
The stylesheet follows a modular approach with:

1. **CSS Variables (`:root`)** - Centralized design tokens for colors, typography, shadows, and transitions
2. **Reset & Base Styles** - Consistent cross-browser styling
3. **Component-Based Sections** - Navigation, Hero, About, Skills, Projects, Contact, Footer
4. **Responsive Design** - Mobile-first approach with breakpoints at 1024px, 768px, and 480px
5. **Animation System** - Keyframes for scroll animations, hover effects, and loading states

Key design patterns:
- CSS Grid and Flexbox for layouts
- CSS custom properties for theming
- Semantic color naming (`--primary-color`, `--text-secondary`)
- Consistent spacing and typography scales

### JavaScript Architecture
The JS file uses vanilla JavaScript with modern ES6+ features:

1. **Navigation System** - Mobile hamburger menu, active link highlighting, smooth scrolling
2. **Animation Framework** - Intersection Observer for scroll-triggered animations
3. **Performance Optimizations** - Debounced scroll events, lazy animations
4. **Accessibility Features** - Keyboard navigation, reduced motion support, focus management
5. **Interactive Elements** - Contact form handling, hover effects, typing animations

Key patterns:
- Event delegation and modular functions
- Progressive enhancement approach
- Performance-conscious scroll handling
- Accessibility-first interactive elements

## Development Guidelines

### Responsive Breakpoints
- **Desktop**: 1200px+ (default)
- **Large Tablet**: 1024px - 1199px
- **Mobile/Tablet**: 768px - 1023px
- **Small Mobile**: 480px - 767px
- **Tiny Mobile**: < 480px

### Color System
Primary colors follow a tech-inspired blue/green theme:
- **Primary**: `#0066cc` (main brand color)
- **Secondary**: `#00b894` (accent green)
- **Background**: `#ffffff` / `#f8f9fa` (primary/secondary)
- **Text**: `#2d3436` / `#636e72` (primary/secondary)

### Animation Principles
- **Performance**: Uses `transform` and `opacity` for GPU acceleration
- **Accessibility**: Respects `prefers-reduced-motion`
- **Timing**: Fast transitions (0.3s) for UI, medium (0.5s) for content
- **Easing**: Consistent `ease` timing function throughout

### Component Architecture
Each section follows this pattern:
1. **Container** (`.container`) - Max-width wrapper with responsive padding
2. **Section Header** (`.section-header`) - Consistent title and subtitle structure  
3. **Content Grid** - CSS Grid layouts for responsive content organization
4. **Interactive Elements** - Hover states, animations, and accessibility features

## Development Tasks

### Adding New Sections
1. Add HTML structure with semantic section tag and unique ID
2. Include `.container` wrapper and `.section-header` if needed
3. Add corresponding CSS in the stylesheet following the established pattern
4. Update navigation links in both HTML and JavaScript active highlighting
5. Add intersection observer for scroll animations if needed

### Updating Content
- **Projects**: Update `.project-card` elements with new GitHub repositories
- **Skills**: Modify `.skill-item` elements in respective categories
- **Contact Info**: Update contact details in both hero and contact sections
- **Social Links**: Update href attributes for GitHub, LinkedIn, email

### Styling Modifications
- **Colors**: Modify CSS variables in `:root` for global color changes
- **Typography**: Update `font-weight` variables and Google Fonts import
- **Spacing**: Adjust container padding and section spacing via CSS variables
- **Animations**: Modify keyframes and transition durations in CSS variables

### Performance Optimizations
- **Images**: Implement lazy loading for any added images
- **CSS**: Use CSS containment for isolated sections
- **JavaScript**: Maintain debounced scroll handlers for performance
- **Accessibility**: Test with screen readers and keyboard navigation

## Browser Support
- **Modern Browsers**: Chrome, Firefox, Safari, Edge (latest versions)
- **CSS Features**: CSS Grid, Flexbox, Custom Properties, Intersection Observer
- **JavaScript**: ES6+, Modern Web APIs
- **Progressive Enhancement**: Graceful degradation for older browsers

## Contact Integration
The contact form uses `mailto:` links for simplicity. For production use with form backends:
1. Replace the form submission handler in `js/script.js`
2. Update the form action and method attributes
3. Add proper form validation and error handling
4. Consider integrations with services like Formspree, Netlify Forms, or custom backend

## Future Enhancements Ready
The codebase includes preparation for:
- **Dark/Light Theme Toggle**: CSS variables and JavaScript theme switching foundation
- **Progressive Web App**: Service worker implementation ready
- **Blog Section**: Extensible section structure for content addition
- **Multi-language Support**: Internationalization structure consideration
- **Advanced Animations**: GSAP or Framer Motion integration points identified

## Git Workflow
Standard web development workflow:
1. Create feature branches for new sections or major updates
2. Test responsive design across all breakpoints
3. Validate HTML, CSS, and JavaScript
4. Test accessibility with screen readers
5. Verify cross-browser compatibility before merging
