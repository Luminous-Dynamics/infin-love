# Contribution Checklists 📋

> Quick reference checklists for different types of contributions

This document provides ready-to-use checklists for common contribution types. Copy the relevant checklist into your PR description or use it to guide your work.

**See also:** [CONTRIBUTING.md](../CONTRIBUTING.md) • [EXAMPLES.md](../EXAMPLES.md) • [QUICK_START.md](../QUICK_START.md)

---

## Table of Contents

1. [Code Contribution Checklist](#code-contribution-checklist)
2. [Documentation Contribution Checklist](#documentation-contribution-checklist)
3. [Design/UI Contribution Checklist](#designui-contribution-checklist)
4. [Accessibility Enhancement Checklist](#accessibility-enhancement-checklist)
5. [Bug Fix Checklist](#bug-fix-checklist)
6. [Performance Optimization Checklist](#performance-optimization-checklist)

---

## Code Contribution Checklist

**For:** Adding new features or functionality

### Before Starting
- [ ] Read [ARCHITECTURE.md](../ARCHITECTURE.md) to understand system design
- [ ] Check [DESIGN.md](../DESIGN.md) for design system tokens
- [ ] Review [EXAMPLES.md](../EXAMPLES.md) for code patterns
- [ ] Search existing issues/PRs for similar work

### During Development
- [ ] Follow existing code style (4 spaces, meaningful names)
- [ ] Use semantic HTML5 elements
- [ ] Add ARIA labels where needed
- [ ] Test keyboard navigation
- [ ] Ensure mobile responsiveness
- [ ] Add comments for complex logic
- [ ] Keep accessibility-first approach

### Testing
- [ ] Test in Chrome/Firefox/Safari/Edge
- [ ] Test on mobile device or emulator
- [ ] Test keyboard-only navigation
- [ ] Run HTML validator (no errors)
- [ ] Check browser console (no errors)
- [ ] Verify Lighthouse scores remain 95+
- [ ] Test with screen reader if possible

### Before Submitting
- [ ] Remove any console.log statements
- [ ] Update relevant documentation
- [ ] Add yourself to CONTRIBUTORS.md
- [ ] Write clear commit message
- [ ] Fill out PR template completely
- [ ] Link related issue (if applicable)

---

## Documentation Contribution Checklist

**For:** Improving or creating documentation

### Before Starting
- [ ] Read [INDEX.md](../INDEX.md) to understand documentation structure
- [ ] Check existing docs for similar content
- [ ] Review [GLOSSARY.md](../GLOSSARY.md) for terminology
- [ ] Note where your doc fits in the ecosystem

### Writing
- [ ] Use clear, concise language
- [ ] Add table of contents for long docs (>200 lines)
- [ ] Include code examples where helpful
- [ ] Cross-reference related documentation
- [ ] Use inclusive, welcoming language
- [ ] Add emojis sparingly for visual navigation
- [ ] Follow existing markdown formatting

### Quality Checks
- [ ] Spell check (will be automated on PR)
- [ ] Grammar check
- [ ] Links work correctly
- [ ] Code examples are accurate
- [ ] Screenshots included (if visual content)
- [ ] Accessibility of any images/diagrams

### Integration
- [ ] Add to INDEX.md in appropriate section(s)
- [ ] Update PROJECT_STATUS.md if adding major doc
- [ ] Cross-reference from related docs
- [ ] Add terms to GLOSSARY.md if needed
- [ ] Update .wordlist.txt for new terms

---

## Design/UI Contribution Checklist

**For:** Visual design changes or improvements

### Before Starting
- [ ] Review [DESIGN.md](../DESIGN.md) for design system
- [ ] Understand color palette and tokens
- [ ] Check typography system
- [ ] Note spacing/sizing scale
- [ ] Review existing UI patterns

### Design Work
- [ ] Use existing color variables
- [ ] Follow typography scale
- [ ] Maintain spacing consistency
- [ ] Ensure mobile-first design
- [ ] Keep sacred aesthetic
- [ ] Preserve accessibility

### Accessibility Requirements
- [ ] Color contrast ≥ 4.5:1 (WCAG AA)
- [ ] Touch targets ≥ 44x44px
- [ ] Focus states clearly visible
- [ ] Works without color alone
- [ ] Maintains keyboard navigation
- [ ] Screen reader friendly

### Testing
- [ ] Test on multiple screen sizes
- [ ] Test with color blindness simulators
- [ ] Verify in different browsers
- [ ] Check dark backgrounds (if applicable)
- [ ] Test animations for accessibility
- [ ] Verify print styles

### Documentation
- [ ] Add screenshots (before/after)
- [ ] Document new design tokens
- [ ] Update DESIGN.md if needed
- [ ] Note any breaking changes

---

## Accessibility Enhancement Checklist

**For:** Improving accessibility compliance

### Assessment
- [ ] Run axe DevTools scan
- [ ] Run WAVE browser extension
- [ ] Test keyboard navigation
- [ ] Test with screen reader (NVDA/JAWS/VoiceOver)
- [ ] Check color contrast
- [ ] Verify focus management
- [ ] Review ARIA usage

### Common Fixes
- [ ] Add missing alt text to images
- [ ] Improve ARIA labels
- [ ] Fix heading hierarchy
- [ ] Add skip-to-content links
- [ ] Improve focus indicators
- [ ] Fix keyboard traps
- [ ] Add proper roles and landmarks

### Testing Requirements
- [ ] Tab through entire page (no keyboard traps)
- [ ] Test with screen reader
- [ ] Verify focus visible on all interactive elements
- [ ] Test form validation announcements
- [ ] Check dynamic content announcements
- [ ] Verify button/link semantics

### Documentation
- [ ] Explain what issue was fixed
- [ ] Document testing methodology
- [ ] Note WCAG success criteria met
- [ ] Add to TESTING.md if new pattern

---

## Bug Fix Checklist

**For:** Fixing identified bugs or issues

### Investigation
- [ ] Reproduce the bug consistently
- [ ] Identify root cause
- [ ] Check if bug exists in other browsers/devices
- [ ] Search for related issues
- [ ] Document steps to reproduce

### Fixing
- [ ] Create minimal fix (avoid scope creep)
- [ ] Add comments explaining why fix works
- [ ] Consider edge cases
- [ ] Don't introduce new issues
- [ ] Follow existing code patterns

### Testing
- [ ] Verify bug is fixed
- [ ] Test in all major browsers
- [ ] Test on mobile if applicable
- [ ] Regression test related features
- [ ] Check no new console errors
- [ ] Verify accessibility maintained

### Documentation
- [ ] Link to original issue
- [ ] Explain what caused bug
- [ ] Document the fix approach
- [ ] Note any workarounds removed
- [ ] Update TROUBLESHOOTING.md if helpful

---

## Performance Optimization Checklist

**For:** Improving site performance

### Baseline
- [ ] Run Lighthouse audit (record current scores)
- [ ] Use Chrome DevTools Performance panel
- [ ] Measure page load time
- [ ] Check bundle size
- [ ] Note Time to Interactive (TTI)
- [ ] Identify bottlenecks

### Optimization
- [ ] Optimize images (WebP, compression)
- [ ] Minimize JavaScript
- [ ] Defer non-critical scripts
- [ ] Optimize CSS delivery
- [ ] Reduce animation complexity
- [ ] Implement lazy loading (if applicable)

### Validation
- [ ] Run Lighthouse again (verify improvement)
- [ ] Test on slow 3G connection
- [ ] Verify on low-end devices
- [ ] Check no visual regressions
- [ ] Ensure functionality intact
- [ ] Lighthouse scores ≥ 95

### Documentation
- [ ] Document baseline vs. new performance
- [ ] Explain optimization techniques used
- [ ] Note any trade-offs made
- [ ] Update performance docs if needed

---

## General Best Practices

**For all contributions:**

### Communication
- ✅ Be kind, respectful, inclusive
- ✅ Ask questions if unclear
- ✅ Provide context in PR descriptions
- ✅ Respond to feedback graciously
- ✅ Follow [CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md)

### Quality
- ✅ Test thoroughly before submitting
- ✅ Write clear, descriptive commit messages
- ✅ Keep changes focused and atomic
- ✅ Follow existing patterns and style
- ✅ Update relevant documentation

### Sacred Values
- ✅ Accessibility is non-negotiable
- ✅ Performance matters (respect users' bandwidth)
- ✅ Privacy is sacred (no tracking without consent)
- ✅ Beauty serves function
- ✅ Simplicity over complexity
- ✅ Community over individual

---

## Getting Help

**Stuck on any of these checklists?**

1. **Check documentation:**
   - [TROUBLESHOOTING.md](../TROUBLESHOOTING.md) - Common issues
   - [FAQ.md](../FAQ.md) - Frequently asked questions
   - [EXAMPLES.md](../EXAMPLES.md) - Code patterns
   - [RESOURCES.md](../RESOURCES.md) - External learning

2. **Ask the community:**
   - [Discussions Q&A](https://github.com/Luminous-Dynamics/infin-love/discussions/categories/q-a)
   - Tag maintainers in your PR
   - Email: tristan.stoltz@gmail.com

3. **Learn more:**
   - [LEARNING_PATHS.md](../LEARNING_PATHS.md) - Guided journeys
   - [ONBOARDING.md](../ONBOARDING.md) - Complete contributor guide

---

## Quick Reference

**Most common pre-submission checks:**

```markdown
- [ ] HTML validates (no errors)
- [ ] No console errors
- [ ] Tested keyboard navigation
- [ ] Tested on mobile
- [ ] Lighthouse scores 95+
- [ ] Accessibility maintained
- [ ] Documentation updated
- [ ] PR template filled out
```

---

<div align="center">

**Thank you for contributing with care** 💜

**Your attention to quality makes Infin.Love world-class**

Built with consciousness • Shared with love • Held in sacred reciprocity

[⬆ Back to Top](#contribution-checklists-)

</div>
