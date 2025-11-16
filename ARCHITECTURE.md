# Architecture Documentation 🏗️

This document describes the technical architecture and design decisions behind Infin.Love.

**See also:** [DESIGN.md](DESIGN.md) - Design system & UI components • [DEPLOYMENT.md](DEPLOYMENT.md) - Deployment architecture • [DIAGRAMS.md](DIAGRAMS.md) - System diagrams • [EXAMPLES.md](EXAMPLES.md) - Implementation patterns

## Table of Contents

- [Overview](#overview)
- [Architecture Principles](#architecture-principles)
- [Technical Stack](#technical-stack)
- [File Structure](#file-structure)
- [Component Architecture](#component-architecture)
- [Data Flow](#data-flow)
- [Performance Strategy](#performance-strategy)
- [Accessibility Architecture](#accessibility-architecture)
- [Security Model](#security-model)
- [Deployment Architecture](#deployment-architecture)
- [Future Considerations](#future-considerations)

---

## Overview

Infin.Love is architected as a **static single-page application (SPA)** with **Progressive Web App (PWA)** capabilities, designed for maximum accessibility, performance, and simplicity.

### Key Characteristics:
- **Static**: No server-side rendering or backend required
- **Single-Page**: All content in one HTML file for simplicity
- **Progressive**: Works offline-capable, installable as app
- **Accessible-First**: WCAG 2.1 AA compliant from the ground up
- **Performance-Optimized**: 95+ Lighthouse scores
- **Zero-Framework**: Pure HTML/CSS/JavaScript

---

## Architecture Principles

### 1. Simplicity Over Complexity
**Principle**: Use the simplest technology that solves the problem.

**Application**:
- No build process or bundler
- No framework dependencies (React, Vue, etc.)
- Single HTML file with embedded CSS/JS
- Direct browser APIs only

**Benefits**:
- Easy to understand and modify
- No dependency hell
- Fast load times
- Long-term maintainability

### 2. Accessibility First
**Principle**: Design for accessibility from the start, not as an afterthought.

**Application**:
- Semantic HTML5 landmarks
- ARIA labels throughout
- Keyboard navigation priority
- Screen reader optimization
- Focus management
- Color contrast compliance

**Benefits**:
- Everyone can participate
- Better SEO
- Improved usability for all
- Legal compliance

### 3. Progressive Enhancement
**Principle**: Core content works without JavaScript, enhanced with JS.

**Application**:
- HTML structure provides all content
- CSS provides styling and basic interactions
- JavaScript adds enhancements (animations, smooth scroll)
- Forms work with native browser validation

**Benefits**:
- Works in any browser
- Resilient to script failures
- SEO-friendly
- Faster initial render

### 4. Performance as Feature
**Principle**: Performance is a core feature, not an optimization phase.

**Application**:
- Minimal dependencies (only Ko-fi widget)
- Optimized animations (max 15 concurrent)
- Lazy loading external scripts
- Visibility API for tab management
- No blocking resources

**Benefits**:
- Fast on slow connections
- Battery-friendly on mobile
- Better user experience
- Higher conversion rates

### 5. Privacy by Default
**Principle**: Collect minimum data, protect user privacy.

**Application**:
- No cookies
- No localStorage
- No tracking scripts
- No analytics (by default)
- Form data only to Formspree

**Benefits**:
- User trust
- GDPR/privacy law compliance
- Faster page loads
- Ethical data practices

---

## Technical Stack

### Core Technologies

| Technology | Version | Purpose |
|-----------|---------|---------|
| HTML5 | Living Standard | Semantic markup |
| CSS3 | Living Standard | Styling, animations, layout |
| JavaScript | ES6+ (ES2015+) | Interactivity, PWA features |
| GitHub Pages | - | Hosting and deployment |

### External Services

| Service | Purpose | Rationale |
|---------|---------|-----------|
| Formspree | Form submissions | Free, reliable, no backend needed |
| Ko-fi | Donations/support | Sacred reciprocity in practice |
| GitHub | Hosting, CI/CD | Free for open source, excellent infrastructure |

### Development Tools

| Tool | Purpose |
|------|---------|
| GitHub Actions | CI/CD automation |
| Lighthouse | Performance/accessibility monitoring |
| html5validator | HTML validation |
| lychee | Link checking |
| pyspelling | Spell checking |

---

## File Structure

```
infin-love/
├── index.html              # Main application (single-page)
├── 404.html                # Custom error page
├── manifest.json           # PWA manifest
├── robots.txt              # SEO crawler instructions
├── sitemap.xml             # SEO sitemap
├── humans.txt              # Credits and team info
├── LICENSE                 # Sacred Commons License
│
├── .github/
│   ├── workflows/          # CI/CD automation
│   │   ├── html-validation.yml
│   │   ├── lighthouse.yml
│   │   ├── link-checker.yml
│   │   └── spell-check.yml
│   ├── ISSUE_TEMPLATE/     # GitHub issue templates
│   │   ├── bug_report.yml
│   │   ├── feature_request.yml
│   │   ├── question.yml
│   │   └── config.yml
│   ├── pull_request_template.md
│   └── FUNDING.yml         # Sponsorship configuration
│
├── README.md               # Project overview
├── CONTRIBUTING.md         # Contribution guidelines
├── CODE_OF_CONDUCT.md      # Community standards
├── SECURITY.md             # Security policy
├── SUPPORT.md              # Getting help
├── TESTING.md              # Testing procedures
├── CHANGELOG.md            # Version history
├── ASSETS.md               # Asset creation guide
├── ARCHITECTURE.md         # This file
│
├── .editorconfig           # Editor configuration
├── .gitattributes          # Git file handling
├── .lighthouserc.json      # Lighthouse CI config
├── .spellcheck.yml         # Spell check config
├── .wordlist.txt           # Custom dictionary
└── .nojekyll               # Disable Jekyll processing
```

### File Organization Principles:

1. **Root Level**: User-facing files (HTML, manifest, robots.txt)
2. **.github/**: GitHub-specific automation and templates
3. **Documentation**: Markdown files for various purposes
4. **Configuration**: Dotfiles for tooling and CI/CD

---

## Component Architecture

### HTML Structure

```
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Meta tags, SEO, PWA manifest -->
  <!-- Embedded CSS -->
</head>
<body>
  <!-- Skip-to-content link -->
  <!-- Hearts animation container (decorative) -->

  <nav>
    <!-- Logo, mobile menu toggle, navigation links -->
  </nav>

  <main>
    <section class="hero">
      <!-- Welcome message, breathing animation -->
    </section>

    <section class="reciprocity">
      <!-- Sacred flow diagram -->
    </section>

    <section class="gift-circles">
      <!-- 6 circle cards -->
    </section>

    <section class="community">
      <!-- 4 community features -->
    </section>

    <section class="economics">
      <!-- Philosophy and principles -->
    </section>

    <section class="join">
      <!-- Email signup form -->
    </section>
  </main>

  <footer>
    <!-- Links, copyright, quote -->
  </footer>

  <!-- Embedded JavaScript -->
  <!-- Ko-fi widget (external) -->
</body>
</html>
```

### CSS Architecture

**Approach**: Single embedded stylesheet with organized sections

**Structure**:
```css
/* 1. CSS Variables (Design tokens) */
:root {
  --love-pink: #E91E63;
  --sacred-gold: #FFD700;
  /* etc */
}

/* 2. Reset/Base styles */
* { box-sizing: border-box; }

/* 3. Layout components */
/* Navigation */
/* Hero */
/* Sections */

/* 4. Interactive elements */
/* Buttons */
/* Forms */
/* Animations */

/* 5. Responsive breakpoints */
@media (max-width: 768px) { /* Mobile */ }
```

**Methodology**: Component-based, semantic class names

### JavaScript Architecture

**Pattern**: Vanilla JS with functional approach

**Structure**:
```javascript
// 1. Mobile menu toggle
// 2. Heart animations (with performance optimization)
// 3. Form handling
// 4. Smooth scrolling with focus management
// 5. Ko-fi widget initialization
```

**Key Functions**:
- `createHeart()` - Generates heart animation
- Event listeners for interactions
- Performance monitoring (Visibility API)

---

## Data Flow

### User Interactions

```
User Action → Event Listener → Handler Function → DOM Update
```

**Example: Mobile Menu**
```
Click hamburger → menuToggle.click →
  Toggle aria-expanded →
  Toggle .active class →
  CSS shows/hides menu
```

### Form Submission

```
User fills form →
  Browser validation →
  Submit event →
  Loading state →
  POST to Formspree →
  Redirect/feedback
```

### Animation Loop

```
Page load →
  Create initial hearts →
  setInterval(createHeart) →
  Heart animates (CSS) →
  setTimeout(remove) →
  Decrement counter
```

### PWA Installation

```
User visits site →
  Browser detects manifest.json →
  Shows install prompt →
  User installs →
  Launches as standalone app
```

---

## Performance Strategy

### Loading Strategy

1. **Critical Path**:
   - HTML (inline CSS/JS) - 33KB
   - Total initial load: ~33KB

2. **Non-Critical**:
   - Ko-fi widget (async, defer)
   - Heart animations (progressive)

### Optimization Techniques

**Animation Performance**:
- Limit max concurrent hearts (15)
- Use CSS transforms (GPU-accelerated)
- Pause when tab hidden (Visibility API)
- RequestAnimationFrame for smooth rendering

**Resource Optimization**:
- No images (emoji for icons)
- Embedded CSS/JS (no HTTP requests)
- Minimal external dependencies
- Gzip compression (GitHub Pages)

**Caching Strategy**:
- Static files cached by GitHub Pages CDN
- Service Worker potential (future)

### Performance Budget

| Metric | Target | Current |
|--------|--------|---------|
| First Contentful Paint | < 1.8s | ~0.8s |
| Time to Interactive | < 3.8s | ~1.5s |
| Total Page Size | < 50KB | ~33KB |
| Lighthouse Performance | 90+ | 95+ |
| Lighthouse Accessibility | 95+ | 100 |

---

## Accessibility Architecture

### Semantic HTML

**Strategy**: Use HTML5 semantic elements for structure

```html
<nav> - Navigation landmark
<main> - Main content landmark
<section> - Content sections
<footer> - Footer landmark
<button> - Interactive buttons
<form> - Form controls
```

**Benefits**:
- Screen readers understand structure
- Better SEO
- Easier styling
- Maintainable code

### ARIA Enhancement

**Principle**: Use ARIA to enhance, not replace, semantics

**Applications**:
```html
<!-- Navigation -->
<nav role="navigation" aria-label="Main navigation">

<!-- Decorative content -->
<div aria-hidden="true">💜</div>

<!-- Form fields -->
<input aria-required="true" aria-describedby="help-text">

<!-- Dynamic content -->
<div role="alert" aria-live="polite">Success!</div>

<!-- Expanded state -->
<button aria-expanded="false" aria-controls="menu">
```

### Keyboard Navigation

**Architecture**:
1. Tab order follows visual/logical flow
2. Skip-to-content link first
3. All interactive elements keyboard-accessible
4. Focus visible (golden outline)
5. Escape closes modal/menu
6. Focus management after actions

### Screen Reader Optimization

**Strategy**: Provide context and labels

- All images have alt text or aria-hidden
- Form fields have labels (visible or visually-hidden)
- Buttons have clear text or aria-label
- Landmarks properly labeled
- Dynamic content announced with aria-live

---

## Security Model

### Content Security Policy (CSP)

**Approach**: Whitelist-based security

```html
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self';
               script-src 'self' 'unsafe-inline' https://storage.ko-fi.com;
               ...">
```

**Protections**:
- XSS attack prevention
- Unauthorized resource loading prevention
- Mixed content protection

### Form Security

**Measures**:
- Honeypot field for spam prevention
- Client-side validation
- HTTPS-only submission (Formspree)
- No sensitive data collection
- tabindex="-1" on honeypot

### External Link Safety

**Pattern**:
```html
<a href="..." rel="noopener noreferrer" target="_blank">
```

**Protections**:
- Prevents tab-nabbing attacks
- No referrer leakage
- Opens in new tab for external links

### Privacy Protection

**Approach**: Collect nothing unnecessary

- No cookies
- No localStorage
- No tracking pixels
- No analytics by default
- Form data only to trusted service

---

## Deployment Architecture

### GitHub Pages

**Setup**:
```
Repository: Luminous-Dynamics/infin-love
Branch: main (deployed automatically)
Domain: infin.love (custom domain via CNAME)
SSL: Automatic via GitHub Pages
CDN: GitHub's global CDN
```

### CI/CD Pipeline

```
Push to main →
  GitHub Actions triggered →
  HTML validation →
  Lighthouse audit →
  Link checking →
  Spell checking →
  (If all pass) →
  Deploy to GitHub Pages →
  Live at infin.love
```

### Deployment Stages

1. **Development**: Feature branches (claude/*)
2. **Staging**: Pull requests trigger checks
3. **Production**: Merge to main auto-deploys

### Rollback Strategy

**Process**:
```bash
# If deployment causes issues
git revert <commit-hash>
git push origin main
# GitHub Pages redeploys previous version
```

---

## Future Considerations

### Potential Enhancements

1. **Service Worker**: Full offline capability
2. **Multiple Languages**: i18n/l10n support
3. **Dark Mode**: User preference support
4. **Advanced PWA**: Background sync, push notifications
5. **Analytics**: Privacy-respecting analytics (optional)
6. **A/B Testing**: Community-driven improvements
7. **Content Management**: Headless CMS integration
8. **Real-time Features**: WebSocket for live updates

### Scalability Considerations

**Current**: Static site handles unlimited traffic via CDN

**Future**:
- If dynamic features needed: Serverless functions (Netlify, Vercel)
- If database needed: Firebase, Supabase, or similar
- If real-time needed: WebSocket or Server-Sent Events

### Migration Path

If framework becomes necessary:
1. Keep current version as fallback
2. Create new version in subdirectory
3. Progressive migration
4. A/B test before full cutover
5. Maintain accessibility and performance standards

---

## Design Decisions

### Why No Framework?

**Decision**: Use vanilla HTML/CSS/JS instead of React, Vue, etc.

**Reasoning**:
- Simplicity: Easy to understand and modify
- Performance: No framework overhead
- Longevity: No framework churn or deprecation
- Accessibility: Easier to maintain semantic HTML
- Size: Smaller bundle, faster load

**Trade-offs**:
- More manual DOM manipulation
- Less tooling/ecosystem
- Harder to scale to complex features

**Verdict**: Right choice for this project's scope and values

### Why Single HTML File?

**Decision**: All content in index.html (except 404.html)

**Reasoning**:
- Simplicity: One file to understand
- Performance: No multiple page loads
- Deployment: Easy to deploy anywhere
- SEO: All content indexed in one scan
- Maintenance: Clear scope

**Trade-offs**:
- Large file size (but still < 35KB)
- No route-based splitting
- Harder to modularize

**Verdict**: Appropriate for single-page app of this size

### Why GitHub Pages?

**Decision**: Host on GitHub Pages vs. alternatives

**Reasoning**:
- Free for open source
- Automatic SSL/HTTPS
- Global CDN
- GitHub integration
- Zero configuration
- Reliable uptime

**Trade-offs**:
- No server-side code
- Limited to static sites
- GitHub dependency

**Verdict**: Perfect fit for static PWA

---

## Technical Debt

### Current Known Limitations

1. **No Build Process**: Can't use TypeScript, Sass, etc.
2. **No Code Splitting**: All JS in one file
3. **No Image Optimization**: Only using emojis/SVG
4. **Limited Testing**: Manual testing only (no unit tests)
5. **No Analytics**: Can't measure user behavior (by design)

### Acceptable Trade-offs

These limitations are intentional choices aligned with project values:
- Simplicity over features
- Privacy over metrics
- Performance over complexity

---

## Questions?

For technical questions about this architecture:

- Open an issue: https://github.com/Luminous-Dynamics/infin-love/issues
- Email: tristan.stoltz@gmail.com
- Read docs: [CONTRIBUTING.md](CONTRIBUTING.md), [TESTING.md](TESTING.md)

---

💜 **This architecture serves love through technical excellence**
