# Code Examples 💻

> *Practical patterns for contributing to Infin.Love*

This guide provides real-world code examples for common contribution tasks. Each example follows our design system, accessibility standards, and gift economy values.

**See also:** [DESIGN.md](DESIGN.md) • [CONTRIBUTING.md](CONTRIBUTING.md) • [QUICK_START.md](QUICK_START.md) • [TROUBLESHOOTING.md](TROUBLESHOOTING.md)

---

## Table of Contents

1. [HTML Patterns](#html-patterns)
2. [CSS Patterns](#css-patterns)
3. [JavaScript Patterns](#javascript-patterns)
4. [Accessibility Patterns](#accessibility-patterns)
5. [Git Workflow Examples](#git-workflow-examples)
6. [Documentation Examples](#documentation-examples)
7. [Common Contribution Patterns](#common-contribution-patterns)

---

## HTML Patterns

### Adding a New Section

**Good example** (semantic, accessible, follows design system):

```html
<section id="new-feature" class="content-section" aria-labelledby="new-feature-heading">
    <div class="container">
        <h2 id="new-feature-heading" class="section-title">
            Your Feature Title
        </h2>

        <p class="section-description">
            Clear, concise description of this section's purpose.
        </p>

        <div class="feature-grid">
            <!-- Feature items here -->
        </div>
    </div>
</section>
```

**Why this works:**
- ✅ Uses semantic `<section>` element
- ✅ Unique `id` for navigation
- ✅ ARIA label references heading
- ✅ Follows `.container` → `.section-title` pattern
- ✅ Uses existing design system classes

**Common mistakes to avoid:**

```html
<!-- ❌ DON'T: Generic divs without semantic meaning -->
<div class="my-section">
    <div class="title">Title</div>
</div>

<!-- ❌ DON'T: Missing accessibility attributes -->
<section>
    <h2>Title</h2>
</section>

<!-- ❌ DON'T: Inline styles instead of classes -->
<section style="background: pink; padding: 20px;">
```

### Creating a Card Component

```html
<article class="gift-card" aria-labelledby="card-title-1">
    <div class="card-icon" aria-hidden="true">
        🌟
    </div>

    <h3 id="card-title-1" class="card-title">
        Card Title
    </h3>

    <p class="card-description">
        Description text that explains the card's purpose and value.
    </p>

    <a href="#details" class="card-link">
        Learn More
        <span class="visually-hidden">about Card Title</span>
    </a>
</article>
```

**Key techniques:**
- Icon uses `aria-hidden="true"` (decorative only)
- Link has hidden text for screen reader context
- `<article>` for self-contained content
- Follows `.card-*` naming pattern

### Form Input with Accessibility

```html
<div class="form-group">
    <label for="user-email" class="form-label">
        Email Address
        <span class="required" aria-label="required">*</span>
    </label>

    <input
        type="email"
        id="user-email"
        name="email"
        class="form-input"
        required
        aria-required="true"
        aria-describedby="email-help"
        autocomplete="email"
        placeholder="you@example.com"
    >

    <p id="email-help" class="form-help">
        We'll never share your email. See our privacy policy.
    </p>

    <div id="email-error" class="form-error" role="alert" aria-live="polite">
        <!-- Error message injected by JavaScript -->
    </div>
</div>
```

**Accessibility features:**
- Explicit `<label>` with `for` attribute
- `aria-required` matches `required` attribute
- Help text linked with `aria-describedby`
- Error container uses `role="alert"` for announcements
- Proper `autocomplete` attribute for autofill

---

## CSS Patterns

### Using Design System Variables

```css
/* ✅ GOOD: Use CSS custom properties from design system */
.my-component {
    /* Colors from design system */
    background: var(--gradient-purple-pink);
    color: var(--text-light);
    border: 2px solid var(--primary-color);

    /* Spacing from design system */
    padding: var(--space-4);
    margin-bottom: var(--space-6);
    gap: var(--space-3);

    /* Typography from design system */
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-semibold);
    line-height: var(--line-height-relaxed);

    /* Border radius from design system */
    border-radius: var(--border-radius-lg);

    /* Shadows from design system */
    box-shadow: var(--shadow-md);
}
```

```css
/* ❌ BAD: Hardcoded values */
.my-component {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #FFFFFF;
    padding: 16px;
    font-size: 18px;
    border-radius: 12px;
}
```

**Find all available variables in [DESIGN.md](DESIGN.md)**

### Responsive Design Pattern

```css
.feature-grid {
    display: grid;
    gap: var(--space-6);

    /* Mobile first: 1 column */
    grid-template-columns: 1fr;

    /* Tablet: 2 columns */
    @media (min-width: 768px) {
        grid-template-columns: repeat(2, 1fr);
    }

    /* Desktop: 3 columns */
    @media (min-width: 1024px) {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

**Key principles:**
- Start with mobile layout (mobile-first)
- Use design system breakpoints
- Use design system spacing variables
- CSS Grid for modern layouts

### Smooth Animation

```css
.interactive-element {
    /* Set initial state */
    transform: scale(1);
    opacity: 1;

    /* Smooth transition */
    transition:
        transform var(--transition-normal) var(--ease-out),
        opacity var(--transition-normal) var(--ease-out);

    /* Respect reduced motion preference */
    @media (prefers-reduced-motion: reduce) {
        transition: none;
    }
}

.interactive-element:hover,
.interactive-element:focus {
    transform: scale(1.05);
    opacity: 0.9;
}

.interactive-element:active {
    transform: scale(0.98);
}
```

**Animation best practices:**
- Only animate `transform` and `opacity` (performant)
- Use design system transition variables
- Always include `prefers-reduced-motion`
- Provide hover AND focus states

### Accessible Focus States

```css
.button {
    /* Remove default outline */
    outline: none;

    /* Custom focus ring */
    position: relative;
}

.button:focus-visible {
    outline: 3px solid var(--primary-color);
    outline-offset: 3px;
}

/* Alternative: box-shadow approach */
.card:focus-visible {
    box-shadow:
        0 0 0 3px var(--background-color),
        0 0 0 6px var(--primary-color);
}
```

**Why `:focus-visible`:**
- Only shows focus ring for keyboard navigation
- Doesn't show for mouse clicks
- Better user experience overall

---

## JavaScript Patterns

### Smooth Scroll to Section

```javascript
// ✅ GOOD: Accessible smooth scroll with focus management
function scrollToSection(targetId) {
    const target = document.getElementById(targetId);

    if (!target) {
        console.warn(`Target element #${targetId} not found`);
        return;
    }

    // Smooth scroll
    target.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
    });

    // Set focus for keyboard users
    target.setAttribute('tabindex', '-1');
    target.focus();

    // Remove tabindex after focus
    target.addEventListener('blur', function removeFocus() {
        target.removeAttribute('tabindex');
        target.removeEventListener('blur', removeFocus);
    });
}

// Usage in navigation
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', (e) => {
        e.preventDefault();
        const targetId = anchor.getAttribute('href').slice(1);
        scrollToSection(targetId);
    });
});
```

**Key features:**
- Error handling if target doesn't exist
- Focus management for screen readers
- Cleans up temporary `tabindex`
- Works with keyboard and mouse

### Form Validation with Accessibility

```javascript
function validateEmail(input) {
    const email = input.value.trim();
    const errorContainer = document.getElementById(`${input.id}-error`);

    // Clear previous error
    errorContainer.textContent = '';
    input.setAttribute('aria-invalid', 'false');
    input.classList.remove('input-error');

    // Validate
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

    if (!email) {
        showError(input, errorContainer, 'Email is required');
        return false;
    }

    if (!emailRegex.test(email)) {
        showError(input, errorContainer, 'Please enter a valid email address');
        return false;
    }

    return true;
}

function showError(input, errorContainer, message) {
    errorContainer.textContent = message;
    input.setAttribute('aria-invalid', 'true');
    input.classList.add('input-error');

    // Announce to screen readers
    errorContainer.setAttribute('role', 'alert');
}

// Usage
const emailInput = document.getElementById('user-email');
emailInput.addEventListener('blur', () => validateEmail(emailInput));
```

**Accessibility highlights:**
- Uses `aria-invalid` to indicate errors
- Error container has `role="alert"` for announcements
- Visual AND semantic error indication
- Validates on blur (not every keystroke)

### Managing Animations Responsibly

```javascript
// Check user's motion preference
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

function createHeartAnimation() {
    // Respect user preference
    if (prefersReducedMotion) {
        return; // Don't create animation
    }

    const heart = document.createElement('div');
    heart.className = 'floating-heart';
    heart.textContent = '💜';
    heart.setAttribute('aria-hidden', 'true'); // Decorative only

    // Random position
    heart.style.left = Math.random() * 100 + '%';

    document.body.appendChild(heart);

    // Remove after animation completes
    heart.addEventListener('animationend', () => {
        heart.remove();
    });
}

// Limit total animations
const MAX_HEARTS = 15;
let currentHearts = 0;

function createHeartIfPossible() {
    if (currentHearts < MAX_HEARTS) {
        createHeartAnimation();
        currentHearts++;

        setTimeout(() => currentHearts--, 3000); // Decrement after animation
    }
}
```

**Performance best practices:**
- Check `prefers-reduced-motion`
- Mark decorative elements `aria-hidden`
- Limit concurrent animations
- Clean up after animations complete
- Use `animationend` event for cleanup

### Pause Animations When Tab Not Visible

```javascript
// Pause animations when user switches tabs
document.addEventListener('visibilitychange', () => {
    if (document.hidden) {
        // Tab is hidden - pause animations
        pauseAllAnimations();
    } else {
        // Tab is visible - resume animations
        resumeAllAnimations();
    }
});

function pauseAllAnimations() {
    clearInterval(animationInterval);
    document.documentElement.classList.add('animations-paused');
}

function resumeAllAnimations() {
    if (!prefersReducedMotion) {
        animationInterval = setInterval(createHeartIfPossible, 2000);
        document.documentElement.classList.remove('animations-paused');
    }
}
```

---

## Accessibility Patterns

### Visually Hidden Text (for screen readers)

```css
/* CSS for screen-reader-only text */
.visually-hidden {
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

.visually-hidden:focus {
    /* Make visible when focused (e.g., skip links) */
    position: static;
    width: auto;
    height: auto;
    padding: inherit;
    margin: inherit;
    overflow: visible;
    clip: auto;
    white-space: normal;
}
```

```html
<!-- Usage examples -->
<button>
    <span aria-hidden="true">❤️</span>
    <span class="visually-hidden">Add to favorites</span>
</button>

<a href="#main-content" class="visually-hidden skip-link">
    Skip to main content
</a>
```

### Keyboard Navigation

```javascript
// Trap focus within modal dialog
function trapFocus(element) {
    const focusableElements = element.querySelectorAll(
        'a[href], button:not([disabled]), textarea, input, select'
    );

    const firstFocusable = focusableElements[0];
    const lastFocusable = focusableElements[focusableElements.length - 1];

    element.addEventListener('keydown', (e) => {
        if (e.key === 'Tab') {
            if (e.shiftKey) {
                // Shift + Tab
                if (document.activeElement === firstFocusable) {
                    e.preventDefault();
                    lastFocusable.focus();
                }
            } else {
                // Tab
                if (document.activeElement === lastFocusable) {
                    e.preventDefault();
                    firstFocusable.focus();
                }
            }
        }

        // Close on Escape
        if (e.key === 'Escape') {
            closeModal();
        }
    });
}
```

### ARIA Live Regions

```html
<!-- For dynamic status messages -->
<div role="status" aria-live="polite" aria-atomic="true" class="status-message">
    <!-- Content injected by JavaScript -->
</div>

<!-- For critical alerts -->
<div role="alert" aria-live="assertive" class="error-message">
    <!-- Error messages appear here -->
</div>
```

```javascript
// Announce message to screen readers
function announceMessage(message, isError = false) {
    const container = isError
        ? document.querySelector('[role="alert"]')
        : document.querySelector('[role="status"]');

    container.textContent = message;

    // Clear after announcement
    setTimeout(() => {
        container.textContent = '';
    }, 5000);
}

// Usage
announceMessage('Form submitted successfully!');
announceMessage('Please correct the errors below', true);
```

---

## Git Workflow Examples

### Creating a Feature Branch

```bash
# 1. Ensure you're on main and up to date
git checkout main
git pull origin main

# 2. Create feature branch (use conventional naming)
git checkout -b feat/add-testimonials-section

# 3. Make your changes
# Edit files...

# 4. Stage and commit
git add .
git commit -m "feat: add testimonials section with quotes

- Add testimonials section to index.html
- Style testimonial cards with design system
- Ensure WCAG 2.1 AA compliance
- Test on mobile and desktop

Closes #42"

# 5. Push to your fork
git push origin feat/add-testimonials-section

# 6. Create pull request on GitHub
```

### Commit Message Examples

**Good commit messages** (follow Conventional Commits):

```bash
# Feature addition
git commit -m "feat: add dark mode toggle to settings"

# Bug fix
git commit -m "fix: resolve mobile menu not closing on link click

- Add event listener to close menu after navigation
- Test on iOS Safari and Android Chrome

Fixes #123"

# Documentation
git commit -m "docs: update CONTRIBUTING.md with new PR template"

# Style/formatting (no functional change)
git commit -m "style: improve button hover states for consistency"

# Refactoring
git commit -m "refactor: consolidate form validation into utility module"

# Tests
git commit -m "test: add accessibility tests for navigation"

# Chore (maintenance, dependencies)
git commit -m "chore: update dependencies to latest versions"
```

**Commit types:**
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation only
- `style:` - Code style (formatting, no logic change)
- `refactor:` - Code restructuring (no feature change)
- `test:` - Adding or updating tests
- `chore:` - Maintenance tasks

### Updating Your Branch

```bash
# Keep your feature branch up to date with main
git checkout feat/your-feature
git fetch origin
git rebase origin/main

# If conflicts occur:
# 1. Resolve conflicts in your editor
# 2. Stage resolved files
git add .
# 3. Continue rebase
git rebase --continue

# Force push (your branch only!)
git push --force-with-lease origin feat/your-feature
```

---

## Documentation Examples

### Writing Clear Markdown Headers

```markdown
# Main Title (Only One Per Document)

## Major Section

### Subsection

#### Minor Subsection

**General guidelines:**
- Use sentence case (not Title Case)
- Be descriptive and specific
- Include emoji if it aids scanning (optional)
- Keep hierarchy logical (don't skip levels)
```

### Creating Expandable FAQ Items

```markdown
<details>
<summary><strong>How do I get started contributing?</strong></summary>

Start with these steps:

1. Read [QUICK_START.md](QUICK_START.md) (5 minutes)
2. Browse [good first issues](link)
3. Comment on an issue to claim it
4. Follow the contribution workflow

**Need help?** Ask in [Discussions](link)!

</details>
```

**Result:** Expandable/collapsible content that keeps docs scannable

### Writing Helpful Code Comments

```javascript
/**
 * Creates a floating heart animation with performance optimization
 *
 * @param {string} emoji - The emoji to animate (default: '💜')
 * @param {number} duration - Animation duration in ms (default: 3000)
 * @returns {HTMLElement} The created heart element
 *
 * @example
 * createFloatingHeart('❤️', 2000);
 */
function createFloatingHeart(emoji = '💜', duration = 3000) {
    // Implementation...
}
```

```css
/*
 * Gift Circle Cards
 *
 * Displays individual gift circles with hover effects
 * Responsive: 1 column mobile, 2 tablet, 3 desktop
 * Accessibility: High contrast, focus visible
 */
.gift-card {
    /* Styles... */
}
```

---

## Common Contribution Patterns

### Adding a New Gift Circle

**1. Add HTML structure:**

```html
<article class="circle-card" data-circle="new-circle">
    <div class="circle-icon" aria-hidden="true">
        🌟
    </div>

    <h3 class="circle-name">Your Circle Name</h3>

    <p class="circle-description">
        Brief description of what this circle offers.
    </p>

    <ul class="circle-features">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
    </ul>
</article>
```

**2. Add CSS if needed** (usually existing styles work):

```css
/* Only if custom styling needed */
.circle-card[data-circle="new-circle"] {
    /* Custom styles */
}
```

**3. Update documentation:**
- Add to README.md (list of circles)
- Add to COMMUNITY.md (circle guidelines)
- Update FAQ.md if needed

**4. Test accessibility:**
```bash
# Test keyboard navigation
# Test with screen reader
# Validate HTML
# Run Lighthouse audit
```

### Fixing a Typo

**Simplest contribution:**

```bash
# 1. Create branch
git checkout -b docs/fix-typo-in-readme

# 2. Edit file (fix typo)

# 3. Commit
git commit -am "docs: fix typo in README installation section"

# 4. Push
git push origin docs/fix-typo-in-readme

# 5. Create PR
```

**Even tiny fixes are valuable gifts!**

### Improving Accessibility

**Example: Adding alt text to images**

```html
<!-- ❌ Before: Missing alt text -->
<img src="logo.png">

<!-- ✅ After: Descriptive alt text -->
<img src="logo.png" alt="Infin.Love logo - infinity symbol with heart">

<!-- ✅ For decorative images -->
<img src="decoration.png" alt="" aria-hidden="true">
```

**Example: Improving form labels**

```html
<!-- ❌ Before: Placeholder as label -->
<input type="text" placeholder="Enter your name">

<!-- ✅ After: Proper label -->
<label for="user-name">Name</label>
<input type="text" id="user-name" placeholder="Enter your name">
```

### Optimizing Performance

**Example: Lazy loading images**

```html
<!-- For images below the fold -->
<img
    src="small-placeholder.jpg"
    data-src="large-image.jpg"
    alt="Description"
    loading="lazy"
    width="800"
    height="600"
>
```

**Example: Deferring non-critical scripts**

```html
<!-- Load after page renders -->
<script src="analytics.js" defer></script>

<!-- Load asynchronously -->
<script src="widget.js" async></script>
```

---

## Testing Your Changes

### Quick Local Testing Checklist

```bash
# 1. Open in browser
open index.html

# 2. Check console for errors (F12 → Console)
# Should be no errors

# 3. Test responsive design
# F12 → Device toolbar → Try different sizes

# 4. Test keyboard navigation
# Tab through entire page
# Enter/Space on buttons
# Escape to close modals

# 5. Test with screen reader (optional but valuable)
# macOS: Cmd+F5 (VoiceOver)
# Windows: Windows+Ctrl+Enter (Narrator)

# 6. Validate HTML
# https://validator.w3.org/

# 7. Run Lighthouse audit (Chrome DevTools)
# F12 → Lighthouse → Generate report
# Aim for 95+ scores
```

### Automated Testing Commands

```bash
# Spell check
npm run spellcheck

# Lighthouse CI (if configured)
npm run lighthouse

# HTML validation
npm run validate

# All checks
npm run test
```

---

## Learning Resources

**Referenced in examples above:**
- [DESIGN.md](DESIGN.md) - Complete design system
- [CONTRIBUTING.md](CONTRIBUTING.md) - Contribution workflow
- [TESTING.md](TESTING.md) - Full testing guide
- [FAQ.md](FAQ.md) - Common questions

**External resources:**
- [MDN Web Docs](https://developer.mozilla.org/) - HTML/CSS/JS reference
- [WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/) - Accessibility standards
- [Conventional Commits](https://www.conventionalcommits.org/) - Commit message format

---

## Getting Help

**Stuck on an example?**
1. Check [FAQ.md](FAQ.md) for common questions
2. Search [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
3. Ask in [Q&A Discussion category](link)
4. Comment on the relevant issue

**Found an error in these examples?**
Please open an issue or PR! Examples should be accurate and helpful.

---

## Contributing to This Guide

These examples evolve! If you:
- Find a clearer way to explain a pattern
- Discover a common contribution type not covered
- Want to add examples for a specific use case

**Please contribute!** This guide is a gift that grows.

---

<div align="center">

**Happy coding!** 💜

*Remember: Every contribution, no matter how small, is a valuable gift to the community.*

**Next steps:** [QUICK_START.md](QUICK_START.md) • [CONTRIBUTING.md](CONTRIBUTING.md) • [Browse Issues](https://github.com/Luminous-Dynamics/infin-love/issues)

</div>
