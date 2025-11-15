# Design System 🎨

> *Every pixel with purpose. Every color with meaning. Design as sacred practice.*

---

## Design Philosophy

Infin.Love's design embodies **sacred reciprocity** through visual language. Our design is:

- **Warm & Welcoming**: Inviting, not intimidating
- **Accessible & Inclusive**: Beautiful for everyone
- **Mindful & Intentional**: Every choice has meaning
- **Joyful & Loving**: Technology can be delightful
- **Simple & Clear**: Complexity serves no one

---

## Design Tokens

### Color Palette

#### Primary Colors

```css
:root {
    /* Primary Pink - Love, Connection, Heart */
    --primary-color: #E91E63;
    --primary-light: #F06292;
    --primary-dark: #C2185B;

    /* Secondary Pink - Softness, Warmth */
    --secondary-color: #F06292;
    --secondary-light: #F8BBD0;
    --secondary-dark: #EC407A;
}
```

**Usage:**
- **Primary (#E91E63)**: Main brand color, CTAs, links, accents
- **Primary Light (#F06292)**: Gradients, hover states, backgrounds
- **Primary Dark (#C2185B)**: Active states, emphasis

**Color Meaning:**
- **Pink**: Universal love, compassion, nurturing
- **Gradient**: Spectrum of connection, infinite possibilities
- **Warmth**: Emotional safety, belonging

#### Neutral Colors

```css
:root {
    /* Text */
    --text-primary: #212121;      /* Main text - near black */
    --text-secondary: #757575;    /* Secondary text - gray */
    --text-light: #FFFFFF;        /* Light text on dark bg */

    /* Backgrounds */
    --bg-light: #FFFFFF;          /* Main background */
    --bg-gray: #F5F5F5;           /* Subtle background */
    --bg-dark: #212121;           /* Dark sections */

    /* Borders */
    --border-light: #E0E0E0;      /* Light borders */
    --border-medium: #BDBDBD;     /* Medium borders */
}
```

#### Semantic Colors

```css
:root {
    /* Success */
    --success-color: #4CAF50;
    --success-bg: #E8F5E9;

    /* Warning */
    --warning-color: #FF9800;
    --warning-bg: #FFF3E0;

    /* Error */
    --error-color: #F44336;
    --error-bg: #FFEBEE;

    /* Info */
    --info-color: #2196F3;
    --info-bg: #E3F2FD;
}
```

**Usage:**
- **Success**: Form validation, confirmations
- **Warning**: Cautions, important notices
- **Error**: Form errors, critical alerts
- **Info**: Helpful tips, informational messages

#### Gradient System

```css
/* Primary Gradient - Main hero background */
.gradient-primary {
    background: linear-gradient(135deg,
        #E91E63 0%,
        #F06292 50%,
        #EC407A 100%
    );
}

/* Soft Gradient - Subtle backgrounds */
.gradient-soft {
    background: linear-gradient(135deg,
        #F8BBD0 0%,
        #FCE4EC 100%
    );
}

/* Overlay Gradient - Text readability */
.gradient-overlay {
    background: linear-gradient(180deg,
        rgba(0, 0, 0, 0.3) 0%,
        rgba(0, 0, 0, 0.1) 100%
    );
}
```

#### Color Accessibility

**WCAG 2.1 AA Compliance:**

| Foreground | Background | Contrast Ratio | Rating |
|------------|------------|----------------|--------|
| #212121 | #FFFFFF | 16.1:1 | AAA ✅ |
| #757575 | #FFFFFF | 4.6:1 | AA ✅ |
| #FFFFFF | #E91E63 | 4.5:1 | AA ✅ |
| #FFFFFF | #C2185B | 5.4:1 | AAA ✅ |

**Guidelines:**
- Text on white: Use `--text-primary` (#212121)
- Text on pink gradients: Use white (#FFFFFF)
- Minimum contrast: 4.5:1 for normal text
- Minimum contrast: 3:1 for large text (18pt+)

---

### Typography

#### Font Family

```css
:root {
    /* Primary Font Stack */
    --font-primary: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

    /* Fallback Order:
       1. Segoe UI (Windows, modern)
       2. Tahoma (Windows, legacy)
       3. Geneva (macOS)
       4. Verdana (cross-platform)
       5. sans-serif (system default)
    */
}
```

**Why This Stack:**
- **System fonts**: Fast load, no FOIT/FOUT
- **Widely available**: 95%+ device coverage
- **Readable**: Optimized for screen reading
- **Professional**: Clean, modern appearance
- **Accessible**: Clear at all sizes

#### Font Sizes

```css
:root {
    /* Base */
    --font-size-base: 16px;        /* Body text */

    /* Scale */
    --font-size-xs: 0.75rem;       /* 12px - Tiny text */
    --font-size-sm: 0.875rem;      /* 14px - Small text */
    --font-size-md: 1rem;          /* 16px - Body (base) */
    --font-size-lg: 1.125rem;      /* 18px - Large body */
    --font-size-xl: 1.25rem;       /* 20px - Subheadings */
    --font-size-2xl: 1.5rem;       /* 24px - Small headings */
    --font-size-3xl: 2rem;         /* 32px - Medium headings */
    --font-size-4xl: 2.5rem;       /* 40px - Large headings */
    --font-size-5xl: 3rem;         /* 48px - Hero headings */
}
```

**Typography Scale:**
- Ratio: ~1.125 (Major Second)
- Responsive: Scales down on mobile
- Accessible: Respects user zoom/font size preferences

#### Font Weights

```css
:root {
    --font-weight-normal: 400;     /* Body text */
    --font-weight-medium: 500;     /* Emphasis */
    --font-weight-semibold: 600;   /* Subheadings */
    --font-weight-bold: 700;       /* Headings, strong emphasis */
}
```

**Usage:**
- **400 (Normal)**: Body text, paragraphs
- **500 (Medium)**: Subtle emphasis, labels
- **600 (Semibold)**: Section subheadings, navigation
- **700 (Bold)**: Main headings, buttons, strong emphasis

#### Line Heights

```css
:root {
    --line-height-tight: 1.25;     /* Headings */
    --line-height-normal: 1.5;     /* Body text */
    --line-height-relaxed: 1.75;   /* Long-form content */
}
```

**Readability Guidelines:**
- **Headings**: Tight (1.25) - closer lines, more impactful
- **Body**: Normal (1.5) - comfortable reading
- **Long text**: Relaxed (1.75) - reduces eye strain

#### Text Styles

```css
/* Heading Styles */
h1 {
    font-size: var(--font-size-5xl);  /* 48px */
    font-weight: var(--font-weight-bold);
    line-height: var(--line-height-tight);
    margin-bottom: 1rem;
}

h2 {
    font-size: var(--font-size-4xl);  /* 40px */
    font-weight: var(--font-weight-bold);
    line-height: var(--line-height-tight);
    margin-bottom: 0.75rem;
}

h3 {
    font-size: var(--font-size-3xl);  /* 32px */
    font-weight: var(--font-weight-semibold);
    line-height: var(--line-height-tight);
    margin-bottom: 0.5rem;
}

/* Body Styles */
p {
    font-size: var(--font-size-md);   /* 16px */
    font-weight: var(--font-weight-normal);
    line-height: var(--line-height-normal);
    margin-bottom: 1rem;
}

/* Special Styles */
.lead {
    font-size: var(--font-size-lg);   /* 18px */
    line-height: var(--line-height-relaxed);
}

.small {
    font-size: var(--font-size-sm);   /* 14px */
}
```

**Mobile Responsiveness:**

```css
@media (max-width: 768px) {
    :root {
        /* Scale down headings on mobile */
        --font-size-5xl: 2rem;        /* 48px → 32px */
        --font-size-4xl: 1.75rem;     /* 40px → 28px */
        --font-size-3xl: 1.5rem;      /* 32px → 24px */
    }
}
```

---

### Spacing System

#### Spacing Scale

```css
:root {
    /* Base Unit: 4px */
    --space-1: 0.25rem;    /* 4px */
    --space-2: 0.5rem;     /* 8px */
    --space-3: 0.75rem;    /* 12px */
    --space-4: 1rem;       /* 16px */
    --space-5: 1.25rem;    /* 20px */
    --space-6: 1.5rem;     /* 24px */
    --space-8: 2rem;       /* 32px */
    --space-10: 2.5rem;    /* 40px */
    --space-12: 3rem;      /* 48px */
    --space-16: 4rem;      /* 64px */
    --space-20: 5rem;      /* 80px */
    --space-24: 6rem;      /* 96px */
}
```

**Usage Guide:**
- **--space-1 to --space-3**: Internal component spacing
- **--space-4 to --space-8**: Component margins, padding
- **--space-10 to --space-16**: Section spacing
- **--space-20 to --space-24**: Major layout spacing

#### Layout Spacing

```css
:root {
    /* Container */
    --container-padding: var(--space-6);    /* 24px sides */
    --container-max-width: 1200px;

    /* Sections */
    --section-padding-y: var(--space-16);   /* 64px top/bottom */
    --section-padding-x: var(--space-6);    /* 24px sides */

    /* Grid */
    --grid-gap: var(--space-6);             /* 24px between items */
}

@media (max-width: 768px) {
    :root {
        --section-padding-y: var(--space-12);  /* Smaller on mobile */
        --container-padding: var(--space-4);
    }
}
```

---

### Border Radius

```css
:root {
    --radius-sm: 4px;      /* Subtle rounding */
    --radius-md: 8px;      /* Standard rounding */
    --radius-lg: 12px;     /* Large rounding */
    --radius-xl: 16px;     /* Extra large */
    --radius-full: 9999px; /* Pills, circles */
}
```

**Usage:**
- **sm (4px)**: Input fields, small buttons
- **md (8px)**: Cards, buttons, containers
- **lg (12px)**: Modal dialogs, large cards
- **xl (16px)**: Hero sections, featured content
- **full (9999px)**: Pills, tags, circular avatars

---

### Shadows

```css
:root {
    /* Elevation System */
    --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
    --shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.15);

    /* Special */
    --shadow-inner: inset 0 2px 4px rgba(0, 0, 0, 0.06);
    --shadow-none: none;
}
```

**Usage:**
- **sm**: Subtle depth, hover states
- **md**: Cards, buttons, slight elevation
- **lg**: Modals, dropdowns, popovers
- **xl**: Hero sections, major elements
- **inner**: Input fields, inset elements

---

### Z-Index Scale

```css
:root {
    --z-base: 0;           /* Base layer */
    --z-content: 1;        /* Content above base */
    --z-elevated: 10;      /* Elevated content */
    --z-dropdown: 100;     /* Dropdowns, popovers */
    --z-sticky: 500;       /* Sticky headers */
    --z-modal: 1000;       /* Modal dialogs */
    --z-tooltip: 1500;     /* Tooltips */
    --z-toast: 2000;       /* Notifications */
}
```

**Layering Strategy:**
- Large gaps between levels (for intermediate needs)
- Semantic naming (what, not just number)
- Predictable stacking context

---

## UI Components

### Buttons

#### Primary Button

```css
.button-primary {
    /* Colors */
    background: var(--primary-color);
    color: var(--text-light);
    border: none;

    /* Typography */
    font-size: var(--font-size-md);
    font-weight: var(--font-weight-semibold);

    /* Spacing */
    padding: var(--space-3) var(--space-6);

    /* Shape */
    border-radius: var(--radius-md);

    /* Effects */
    box-shadow: var(--shadow-md);
    transition: all 0.3s ease;
    cursor: pointer;
}

.button-primary:hover {
    background: var(--primary-dark);
    box-shadow: var(--shadow-lg);
    transform: translateY(-2px);
}

.button-primary:active {
    transform: translateY(0);
    box-shadow: var(--shadow-sm);
}

.button-primary:focus {
    outline: 2px solid var(--primary-color);
    outline-offset: 2px;
}
```

#### Button Variants

```css
/* Secondary Button */
.button-secondary {
    background: transparent;
    color: var(--primary-color);
    border: 2px solid var(--primary-color);
}

/* Ghost Button */
.button-ghost {
    background: transparent;
    color: var(--text-primary);
    border: none;
}

/* Button Sizes */
.button-sm {
    padding: var(--space-2) var(--space-4);
    font-size: var(--font-size-sm);
}

.button-lg {
    padding: var(--space-4) var(--space-8);
    font-size: var(--font-size-lg);
}
```

### Form Elements

#### Input Fields

```css
.input {
    /* Box Model */
    width: 100%;
    padding: var(--space-3) var(--space-4);

    /* Typography */
    font-size: var(--font-size-md);
    font-family: inherit;
    color: var(--text-primary);

    /* Appearance */
    background: var(--bg-light);
    border: 1px solid var(--border-medium);
    border-radius: var(--radius-sm);

    /* Interaction */
    transition: border-color 0.2s ease;
}

.input:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(233, 30, 99, 0.1);
}

.input::placeholder {
    color: var(--text-secondary);
    opacity: 0.7;
}

/* Error State */
.input.error {
    border-color: var(--error-color);
}

.input.error:focus {
    box-shadow: 0 0 0 3px rgba(244, 67, 54, 0.1);
}
```

#### Labels

```css
.label {
    display: block;
    margin-bottom: var(--space-2);
    font-size: var(--font-size-sm);
    font-weight: var(--font-weight-medium);
    color: var(--text-primary);
}
```

### Cards

```css
.card {
    /* Container */
    background: var(--bg-light);
    border-radius: var(--radius-lg);
    padding: var(--space-6);

    /* Elevation */
    box-shadow: var(--shadow-md);

    /* Interaction */
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
}
```

### Navigation

```css
.nav {
    display: flex;
    gap: var(--space-6);
    align-items: center;
}

.nav-link {
    color: var(--text-light);
    text-decoration: none;
    font-weight: var(--font-weight-medium);
    transition: color 0.2s ease;
    position: relative;
}

.nav-link:hover {
    color: var(--primary-light);
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    right: 0;
    height: 2px;
    background: currentColor;
    transform: scaleX(0);
    transition: transform 0.2s ease;
}

.nav-link:hover::after {
    transform: scaleX(1);
}
```

---

## Animation & Motion

### Timing Functions

```css
:root {
    --ease-in: cubic-bezier(0.4, 0, 1, 1);
    --ease-out: cubic-bezier(0, 0, 0.2, 1);
    --ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
    --ease-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

### Duration

```css
:root {
    --duration-fast: 150ms;
    --duration-normal: 300ms;
    --duration-slow: 500ms;
}
```

### Common Transitions

```css
/* Hover Effects */
.transition-hover {
    transition: transform var(--duration-normal) var(--ease-out);
}

.transition-hover:hover {
    transform: translateY(-2px);
}

/* Fade In */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.fade-in {
    animation: fadeIn var(--duration-slow) var(--ease-out);
}
```

### Heart Animation

```css
@keyframes float {
    0% {
        transform: translateY(100vh) scale(0);
        opacity: 0;
    }
    10% {
        opacity: 1;
    }
    90% {
        opacity: 1;
    }
    100% {
        transform: translateY(-100vh) scale(1);
        opacity: 0;
    }
}

.heart {
    animation: float 8s linear infinite;
}
```

**Performance:**
- Use `transform` and `opacity` for animations (GPU-accelerated)
- Avoid animating `width`, `height`, `left`, `top`
- Limit concurrent animations (max 15 hearts)
- Pause when tab hidden (Visibility API)

---

## Responsive Design

### Breakpoints

```css
:root {
    --breakpoint-mobile: 768px;
    --breakpoint-tablet: 1024px;
    --breakpoint-desktop: 1280px;
}
```

### Media Queries

```css
/* Mobile First Approach */

/* Base styles: Mobile (< 768px) */
.container {
    padding: var(--space-4);
}

/* Tablet and up (>= 768px) */
@media (min-width: 768px) {
    .container {
        padding: var(--space-6);
    }
}

/* Desktop and up (>= 1280px) */
@media (min-width: 1280px) {
    .container {
        padding: var(--space-8);
    }
}
```

### Responsive Typography

```css
/* Fluid Typography */
h1 {
    font-size: clamp(2rem, 5vw, 3rem);
}

/* Scales from 32px at small screens to 48px at large */
```

---

## Accessibility

### Focus States

```css
/* Visible Focus Indicator */
:focus {
    outline: 2px solid var(--primary-color);
    outline-offset: 2px;
}

/* High Contrast Mode Support */
@media (prefers-contrast: high) {
    :focus {
        outline-width: 3px;
    }
}
```

### Reduced Motion

```css
/* Respect user preferences */
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
    }
}
```

### Screen Reader Only

```css
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border-width: 0;
}
```

---

## Design Patterns

### Sacred Geometry

**Hearts:**
- Symbol of love and connection
- Floating animation represents infinite giving
- Randomized sizes/speeds create organic feel
- Limited quantity prevents overwhelm

**Gradients:**
- Represent spectrum of love
- Soft transitions, never harsh
- Pink to lighter pink: warmth to warmth
- Symbolize infinite possibilities

**Rounded Corners:**
- Softer, more welcoming than sharp angles
- 8px standard: gentle but not excessive
- Represents smooth relationships

### Visual Hierarchy

**Structure:**
1. **Hero Section**: Largest text, strongest visual impact
2. **Section Headings**: Clear separation, easy scanning
3. **Body Content**: Comfortable reading flow
4. **Supporting Elements**: Subtle, non-intrusive

**Emphasis Techniques:**
- **Size**: Larger = more important
- **Weight**: Bolder = more important
- **Color**: Primary color = actionable/important
- **Position**: Top/center = more prominent
- **Space**: More whitespace = more important

### Content Density

**Generous Whitespace:**
- Let content breathe
- Never cramped or overwhelming
- Minimum 24px between major sections
- Maximum ~65 characters per line for readability

---

## Brand Assets

### Logo

**Current:** Text-based "Infin.Love"
**Future:** Custom logo with infinity + heart symbolism

**Usage Guidelines:**
- Maintain clear space around logo
- Don't distort proportions
- Don't change colors (except white on dark bg)
- Minimum size: 120px wide

### Iconography

**Current:** Unicode symbols
- ❤️ Heart (love, giving)
- 💜 Purple Heart (sacred values)
- 🎁 Gift (reciprocity)
- 🌟 Star (special, important)
- 💫 Sparkles (magic, delight)

**Future:** Custom icon set aligned with brand

---

## Design Tools & Resources

### Color Tools
- [Coolors](https://coolors.co/) - Palette generator
- [Contrast Checker](https://webaim.org/resources/contrastchecker/) - WCAG compliance
- [Color Safe](http://colorsafe.co/) - Accessible palettes

### Typography Tools
- [Type Scale](https://type-scale.com/) - Scale calculator
- [Modular Scale](https://www.modularscale.com/) - Ratio-based scales
- [Google Fonts](https://fonts.google.com/) - If we add web fonts

### Design Systems
- [Material Design](https://material.io/design) - Inspiration
- [Tailwind](https://tailwindcss.com/docs) - Token ideas
- [Polaris](https://polaris.shopify.com/) - Patterns

---

## Contributing to Design

### Design Changes

**Before making changes:**
1. Discuss in GitHub Issues/Discussions
2. Consider impact on accessibility
3. Maintain design consistency
4. Test across browsers/devices

**When proposing new patterns:**
1. Show visual mockup
2. Explain rationale
3. Consider edge cases
4. Provide code example
5. Test with real users

### Design Review Checklist

- [ ] Maintains visual consistency
- [ ] Accessible (WCAG 2.1 AA)
- [ ] Responsive (mobile to desktop)
- [ ] Performant (no jank)
- [ ] Meaningful (serves purpose)
- [ ] Simple (not over-designed)
- [ ] Aligned with values (sacred reciprocity)

---

## Future Design Enhancements

### Planned
- Custom logo design
- Icon system (SVG sprite)
- Dark mode support
- More animation patterns
- Print stylesheet

### Under Consideration
- Web font (performance vs. beauty)
- Illustrations (commissioned from artists)
- Video backgrounds (performance concern)
- Interactive elements (mindfully)

---

## Questions?

**Design-related questions:**
- [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
- Email: tristan.stoltz@gmail.com

**See Also:**
- [CONTRIBUTING.md](CONTRIBUTING.md) - How to contribute
- [ACCESSIBILITY.md](TESTING.md#accessibility-testing) - Accessibility standards
- [BROWSERS.md](BROWSERS.md) - Cross-browser compatibility

---

<div align="center">

**Design with love. Code with care. Build with purpose.** 💜

*Every pixel is a prayer. Every interaction is a gift.*

</div>
