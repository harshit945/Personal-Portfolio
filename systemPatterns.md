# System Patterns

## Architecture Overview
Single-page static HTML portfolio with embedded CSS and minimal JavaScript for animations and smooth scrolling.

## Design Patterns

### Layout Structure
- **Fixed Navigation**: Sticky header with smooth scroll anchors
- **Section-Based Layout**: Semantic sections with IDs for navigation
- **Responsive Grid System**: Tailwind CSS utility classes for responsive layouts
- **Z-Index Layering**: Background particles (z-0) → Content sections (z-10) → Navigation (z-50)

### Animation Patterns
1. **Fade-in-up**: Entry animations with staggered delays
   - Applied to hero section elements
   - Uses CSS keyframes with opacity and transform
   
2. **Float Animation**: Continuous vertical movement
   - Background decorative elements
   - 3s infinite ease-in-out
   
3. **Gradient Animation**: Animated background gradient
   - Background position shift
   - 200% size with position animation
   
4. **Hover Effects**: Interactive feedback
   - `hover-lift`: translateY(-5px) with enhanced shadow
   - Transition duration: 0.3s ease
   
5. **Pulse Glow**: Attention-drawing shadow animation
   - Applied to primary CTA button
   - Box-shadow intensity variation

### Color System
```
Primary: #0284c7 (Sky 600)
Secondary: #e0f2fe (Sky 100)
Dark: #0f172a (Slate 900)
Text: Slate scale (800, 600, 500, 400)
Background: Animated gradient (white → sky-100 → sky-50 → white)
```

### Typography
- **Font**: Inter (Google Fonts)
- **Weights**: 300, 400, 600, 800
- **Hierarchy**: 
  - H1: 5xl/7xl (Hero)
  - H2: 3xl (Section headers)
  - H3: xl (Subsections)
  - Body: base/lg

## Component Patterns

### Navigation Component
- Fixed position with backdrop blur
- Responsive: Hidden on mobile, flex on md+
- Smooth scroll behavior via CSS
- Active state management via anchor links

### Hero Section
- Full viewport height
- Centered content with max-width constraint
- Badge → Heading → Description → CTA pattern
- Staggered fade-in animations

### Timeline Component (Experience)
- Left border indicator
- Circular markers for timeline points
- Relative positioning for marker placement
- Active (primary) vs past (gray) states
- Responsive: Stack on mobile, inline on desktop

### Card Components
- Consistent padding: p-8
- Border radius: rounded-2xl
- Shadow: shadow-sm/shadow-xl
- Hover effects: hover-lift class
- Border: border-slate-100

### Particle System
- Absolute positioned container
- Individual particles with:
  - Random sizes (8-15px)
  - Staggered left positions (10%-90%)
  - Animated delays (0-5s)
  - Rising animation (10s infinite)
  - Opacity fade in/out

## State Management
- No client-side state (static HTML)
- Scroll position handled by browser
- Animation states managed via CSS classes
- No JavaScript framework needed

## Performance Patterns
- CDN for Tailwind CSS (lazy evaluation)
- Google Fonts preconnect
- Inline critical CSS (animations, custom styles)
- No JavaScript bundling required
- Minimal DOM manipulation

## Accessibility Patterns
- Semantic HTML5 elements (nav, header, section)
- Proper heading hierarchy (h1 → h2 → h3)
- Color contrast ratios maintained
- Smooth scroll with reduced motion consideration
- Focus states on interactive elements

## Code Organization
```
index.html
├── <head>
│   ├── Meta tags
│   ├── Tailwind config
│   └── Custom CSS (animations, utilities)
└── <body>
    ├── Particle background
    ├── Navigation
    ├── Hero section
    ├── About section
    ├── Experience section
    ├── Research section
    ├── Education section
    └── Contact section
```

## Naming Conventions
- **Classes**: kebab-case for custom utilities
- **IDs**: lowercase for section anchors
- **CSS Variables**: None used (Tailwind config)
- **Animations**: descriptive names (fadeInUp, float, gradient, etc.)

## Browser Compatibility
- Modern browsers (ES6+)
- Flexbox and Grid layouts
- CSS animations and transforms
- Backdrop filter support
- Smooth scroll behavior
