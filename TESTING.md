# Testing Guide 🧪

This document outlines comprehensive testing procedures for Infin.Love to ensure quality, accessibility, and performance.

## Table of Contents

- [Quick Testing Checklist](#quick-testing-checklist)
- [Accessibility Testing](#accessibility-testing)
- [Cross-Browser Testing](#cross-browser-testing)
- [Mobile Testing](#mobile-testing)
- [Performance Testing](#performance-testing)
- [Functional Testing](#functional-testing)
- [Visual Regression Testing](#visual-regression-testing)
- [Automated Testing](#automated-testing)

---

## Quick Testing Checklist

Before submitting any PR, verify these essentials:

- [ ] **Visual**: Site looks correct on mobile and desktop
- [ ] **Functional**: All links and buttons work
- [ ] **Forms**: Email signup submits successfully
- [ ] **Keyboard**: Can navigate entire site with Tab/Enter/Escape
- [ ] **Console**: No JavaScript errors
- [ ] **Validation**: HTML passes W3C validator

---

## Accessibility Testing

Ensuring everyone can access and use Infin.Love.

### 1. Keyboard Navigation

**Goal**: Navigate entire site using only keyboard

**Steps**:
1. Load homepage
2. Press `Tab` repeatedly - verify:
   - Skip-to-content link appears first
   - Focus visible on all interactive elements (golden outline)
   - Focus order follows logical reading order
   - No keyboard traps
3. Test navigation:
   - `Tab` / `Shift+Tab`: Move between elements
   - `Enter` / `Space`: Activate links/buttons
   - `Escape`: Close mobile menu (if open)
4. Test mobile menu:
   - `Tab` to hamburger button
   - `Enter` to open menu
   - `Tab` through menu items
   - `Escape` to close

**Pass Criteria**:
- ✅ All interactive elements reachable
- ✅ Focus always visible
- ✅ Logical tab order
- ✅ No keyboard traps

### 2. Screen Reader Testing

**Tools**:
- **NVDA** (Windows, free): https://www.nvaccess.org/
- **JAWS** (Windows, paid): https://www.freedomscientific.com/
- **VoiceOver** (Mac/iOS, built-in): Cmd+F5 to enable
- **TalkBack** (Android, built-in): Settings → Accessibility

**Steps with NVDA** (Windows):
1. Install and start NVDA
2. Navigate to https://infin.love
3. Use these commands:
   - `Down Arrow`: Read next item
   - `H`: Jump between headings
   - `D`: Jump between landmarks (main, nav, footer)
   - `K`: Jump between links
   - `B`: Jump between buttons
   - `F`: Jump between form fields
4. Verify:
   - Page title announced
   - Landmarks identified (navigation, main, footer)
   - Headings in logical order
   - Links have meaningful text
   - Form fields have labels
   - Images have alt text (or aria-hidden if decorative)
   - ARIA roles and labels work correctly

**Pass Criteria**:
- ✅ All content accessible
- ✅ Meaningful announcements
- ✅ Proper heading hierarchy
- ✅ Forms fully labeled
- ✅ No confusing ARIA usage

### 3. Color Contrast

**Tool**: [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

**Steps**:
1. Check all text/background color combinations:
   - White text on purple/pink gradient
   - Gold text on purple background
   - Form input text color
   - Button text color
2. Verify ratios meet WCAG 2.1 AA:
   - **Normal text**: 4.5:1 minimum
   - **Large text** (18pt+): 3:1 minimum

**Pass Criteria**:
- ✅ All text meets contrast ratio requirements

### 4. Zoom and Text Resize

**Steps**:
1. Test browser zoom:
   - Zoom to 200% (Ctrl/Cmd + plus key)
   - Verify all content still usable
   - No horizontal scrolling on mobile viewport
2. Test text-only zoom:
   - Firefox: View → Zoom → Zoom Text Only
   - Increase to 200%
   - Verify layout doesn't break

**Pass Criteria**:
- ✅ Usable at 200% zoom
- ✅ No content cut off
- ✅ No overlapping elements

### 5. Automated Accessibility Scan

**Tools**:
- **axe DevTools** (browser extension): https://www.deque.com/axe/devtools/
- **WAVE** (browser extension): https://wave.webaim.org/extension/
- **Lighthouse** (in Chrome DevTools)

**Steps**:
1. Install browser extension
2. Load page
3. Run scan
4. Fix all errors
5. Review warnings (may be false positives)

**Pass Criteria**:
- ✅ Zero errors
- ✅ Warnings addressed or documented

---

## Cross-Browser Testing

Test on major browsers to ensure compatibility.

### Desktop Browsers

| Browser | Version | Testing Priority |
|---------|---------|------------------|
| Chrome | Latest | ⭐⭐⭐ High |
| Firefox | Latest | ⭐⭐⭐ High |
| Safari | Latest | ⭐⭐ Medium |
| Edge | Latest | ⭐⭐ Medium |
| Opera | Latest | ⭐ Low |

**Test Matrix**:
- [ ] Chrome (Windows/Mac)
- [ ] Firefox (Windows/Mac)
- [ ] Safari (Mac)
- [ ] Edge (Windows)

**What to Test**:
1. Visual rendering (gradients, transparency, blur effects)
2. Smooth scrolling
3. Form submission
4. Floating heart animations
5. Mobile menu (resize window)
6. Ko-fi widget loads

**Pass Criteria**:
- ✅ Consistent appearance across browsers
- ✅ All functionality works
- ✅ No console errors

### Mobile Browsers

| Browser | Platform | Testing Priority |
|---------|----------|------------------|
| Mobile Safari | iOS | ⭐⭐⭐ High |
| Chrome Mobile | Android | ⭐⭐⭐ High |
| Firefox Mobile | Android | ⭐ Low |
| Samsung Internet | Android | ⭐ Low |

**Test Matrix**:
- [ ] iPhone (Safari)
- [ ] Android phone (Chrome)
- [ ] iPad (Safari)

---

## Mobile Testing

### Responsive Breakpoints

Test at these widths:
- **Mobile**: 320px, 375px, 414px
- **Tablet**: 768px, 1024px
- **Desktop**: 1280px, 1920px

**Chrome DevTools Steps**:
1. Open DevTools (F12)
2. Toggle device toolbar (Ctrl+Shift+M)
3. Select device or enter custom width
4. Test portrait and landscape

### Mobile-Specific Tests

- [ ] **Hamburger Menu**:
  - Opens and closes properly
  - Menu items tappable (not too small)
  - Closes when item clicked
- [ ] **Touch Targets**:
  - All buttons/links at least 44x44px
  - Adequate spacing between tap targets
- [ ] **Scrolling**:
  - Smooth scrolling works
  - No horizontal overflow
  - Fixed nav stays at top
- [ ] **Forms**:
  - Input fields large enough to tap
  - Mobile keyboard doesn't cover inputs
  - Autocorrect doesn't interfere
- [ ] **Performance**:
  - Hearts animation doesn't lag
  - Images load quickly
  - No layout shift

**Pass Criteria**:
- ✅ All interactions easy with touch
- ✅ No pinch-to-zoom needed for content
- ✅ Smooth performance

---

## Performance Testing

Ensure fast, efficient page loads.

### Lighthouse Audit

**Steps**:
1. Open Chrome DevTools (F12)
2. Navigate to Lighthouse tab
3. Select:
   - ☑ Performance
   - ☑ Accessibility
   - ☑ Best Practices
   - ☑ SEO
   - ☐ PWA (optional)
4. Choose "Mobile" or "Desktop"
5. Click "Analyze page load"

**Target Scores**:
- **Performance**: 90+ (95+ ideal)
- **Accessibility**: 95+ (100 ideal)
- **Best Practices**: 90+
- **SEO**: 95+

**Common Issues to Check**:
- Image optimization
- Render-blocking resources
- Unused JavaScript/CSS
- Text compression
- Cache policies

### Manual Performance Checks

- [ ] **First Contentful Paint**: < 1.8s
- [ ] **Time to Interactive**: < 3.8s
- [ ] **Total Page Size**: < 1 MB
- [ ] **Number of Requests**: < 50
- [ ] **Hearts Animation**: Smooth (60 FPS)

**Tools**:
- Chrome DevTools → Performance tab
- Network tab (throttle to "Slow 3G" to test)
- PageSpeed Insights: https://pagespeed.web.dev/

**Pass Criteria**:
- ✅ All Lighthouse scores above targets
- ✅ Page feels fast on slow connections
- ✅ No janky animations

---

## Functional Testing

Test all interactive features.

### Navigation

- [ ] Logo links to homepage
- [ ] Nav links scroll to correct sections
- [ ] Smooth scroll animation works
- [ ] Focus moves to target section
- [ ] Mobile hamburger menu works
- [ ] Footer links open correctly

### Forms

**Email Signup Form**:
1. Test valid submission:
   - Fill in name
   - Fill in email (valid format)
   - Fill in gift message (optional)
   - Submit
   - ✅ Loading state shows ("Joining...")
   - ✅ Success message appears (if testing with live Formspree)
2. Test validation:
   - Leave required fields empty
   - ✅ Browser validation prevents submission
   - Use invalid email format
   - ✅ Browser validation shows error
3. Test honeypot:
   - Honeypot field hidden
   - ✅ Not visible to users
   - ✅ Not tabbable

### Animations

- [ ] Hero text has breathing animation
- [ ] Hearts float upward smoothly
- [ ] Hearts appear on mouse movement (throttled)
- [ ] Animations pause when tab hidden
- [ ] Max 15 hearts enforced (check in DevTools)
- [ ] Cards lift on hover
- [ ] Buttons lift on hover

### External Integrations

- [ ] Ko-fi widget loads
- [ ] Ko-fi button opens donation modal
- [ ] Formspree receives submissions (test mode)
- [ ] All external links open in new tab
- [ ] External links have noopener noreferrer

---

## Visual Regression Testing

Catch unintended visual changes.

### Manual Visual Review

Compare before/after screenshots:
1. Take screenshots of key sections:
   - Hero
   - Navigation
   - Gift Circles grid
   - Form
   - Footer
2. After changes, take same screenshots
3. Compare side-by-side
4. Look for:
   - Layout shifts
   - Color changes
   - Spacing differences
   - Font rendering

### Browser Screenshots

**Full page screenshot in Chrome**:
1. Open DevTools (F12)
2. Press Ctrl+Shift+P (Cmd+Shift+P on Mac)
3. Type "screenshot"
4. Select "Capture full size screenshot"

---

## Automated Testing

Run automated checks on every commit.

### GitHub Actions (CI/CD)

Our automated workflows:

1. **HTML Validation** ([html-validation.yml](../.github/workflows/html-validation.yml))
   - Validates all HTML files
   - Runs on: Push to main/claude branches, PRs

2. **Lighthouse CI** ([lighthouse.yml](../.github/workflows/lighthouse.yml))
   - Performance and accessibility scoring
   - Runs on: Push to main, PRs

3. **Link Checker** ([link-checker.yml](../.github/workflows/link-checker.yml))
   - Finds broken links
   - Runs on: Push, PRs, weekly schedule

4. **Spell Check** ([spell-check.yml](../.github/workflows/spell-check.yml))
   - Checks spelling in docs
   - Runs on: Markdown/HTML changes

**View Results**:
- Go to: https://github.com/Luminous-Dynamics/infin-love/actions
- Click on a workflow run
- Review any failures

### Local Testing Commands

```bash
# Serve locally
python -m http.server 8000
# or
npx serve

# Validate HTML (requires html5validator)
html5validator --root . --also-check-css

# Check links (requires lychee)
lychee './**/*.html' './**/*.md'
```

---

## Testing Checklist Template

Copy this for PRs:

```markdown
### Testing Checklist

#### Functionality
- [ ] All features work as expected
- [ ] No console errors
- [ ] Forms submit successfully
- [ ] Navigation works correctly

#### Accessibility
- [ ] Keyboard navigation works
- [ ] Tested with screen reader
- [ ] Color contrast passes
- [ ] Zoom to 200% works

#### Responsive
- [ ] Mobile (< 768px)
- [ ] Tablet (768px - 1024px)
- [ ] Desktop (> 1024px)
- [ ] Mobile menu functional

#### Browsers
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge

#### Performance
- [ ] Lighthouse score 90+
- [ ] Animations smooth
- [ ] Fast page load
```

---

## Reporting Issues

When you find a bug:

1. **Check existing issues**: https://github.com/Luminous-Dynamics/infin-love/issues
2. **Create bug report** using template
3. **Include**:
   - Browser and version
   - Device type
   - Steps to reproduce
   - Screenshots if visual
   - Console errors if applicable

---

## Resources

### Tools
- [W3C HTML Validator](https://validator.w3.org/)
- [WAVE Accessibility Tool](https://wave.webaim.org/)
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [BrowserStack](https://www.browserstack.com/) (cross-browser testing)

### Guides
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WebAIM Checklist](https://webaim.org/standards/wcag/checklist)
- [MDN Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)

---

💜 **Thank you for helping ensure Infin.Love is accessible and high-quality for everyone!**
