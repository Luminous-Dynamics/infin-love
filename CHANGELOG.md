# Changelog

All notable changes to Infin.Love will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- GitHub Actions CI/CD workflows for automated quality checks
- HTML validation workflow to catch markup errors
- Lighthouse CI for performance and accessibility monitoring
- Link checker workflow to detect broken links
- Spell check workflow for documentation quality
- CHANGELOG.md for version tracking
- Pull request template for consistent contributions
- .editorconfig for consistent code style
- TESTING.md with comprehensive testing procedures

## [1.0.0] - 2025-01-14

### Added - Community Health & Documentation
- **CONTRIBUTING.md**: Comprehensive contribution guidelines with:
  - Development and testing requirements
  - Pull request process and commit standards
  - Sacred values integration
  - Asset creation specifications
- **CODE_OF_CONDUCT.md**: Sacred Covenant of Conduct featuring:
  - Love-based community principles
  - Restorative justice approach
  - Clear reporting procedures
- **SECURITY.md**: Security vulnerability disclosure policy
- **ASSETS.md**: Visual asset creation guide for og-image and logo
- GitHub issue templates:
  - Bug report template with detailed reproduction steps
  - Feature request template with values alignment
  - Question/help template
  - Issue template configuration

### Added - Progressive Web App
- **manifest.json**: PWA manifest enabling:
  - "Add to Home Screen" functionality
  - Standalone app experience on mobile
  - Branded theme colors
- Apple touch icon link in index.html
- Theme color meta tag

### Added - User Experience
- **404.html**: Custom error page with:
  - Beautiful branded design
  - Navigation back to main sections
  - Encouraging messaging
- Mobile hamburger menu for responsive navigation
- Skip-to-content link for keyboard navigation
- Form submission feedback messages
- Loading states for form submission

### Added - SEO & Discoverability
- **README.md**: Comprehensive project documentation
- **robots.txt**: Search engine crawling guidelines
- **sitemap.xml**: XML sitemap with all main sections
- Open Graph metadata for rich social sharing
- Twitter Card support
- JSON-LD structured data
- Canonical URL tags

### Added - Accessibility
- ARIA labels and roles throughout the site
- Semantic HTML5 landmarks (main, nav, footer)
- Visually-hidden form labels for screen readers
- Enhanced focus states with visible outlines
- Keyboard navigation support
- Proper heading hierarchy
- Alt text for meaningful images

### Added - Development
- **.gitattributes**: Consistent line endings across platforms
- **.lighthouserc.json**: Lighthouse CI configuration
- **.spellcheck.yml**: Spell check configuration
- **.wordlist.txt**: Custom dictionary for technical terms

### Changed
- Navigation is now sticky for better UX
- Copyright year updates dynamically
- Improved smooth scrolling with proper focus management
- Ko-fi widget loads asynchronously for better performance
- Mobile navigation uses dropdown menu instead of hidden links

### Improved - Performance
- Limited max concurrent heart animations (15 max)
- Consolidated animation intervals
- Added Visibility API to pause animations when tab is hidden
- Deferred external script loading
- Reduced initial heart count from 8 to 5

### Improved - Security
- Added Content Security Policy (CSP) meta tag
- rel="noopener noreferrer" on all external links
- Enhanced form security attributes (tabindex, autocomplete)
- Honeypot field for spam prevention

### Fixed
- Mobile navigation now accessible on small screens
- Form validation properly integrated with ARIA
- Screen reader accessibility throughout site
- Focus management for keyboard users

## [0.1.0] - 2025-01-01 (Initial Release)

### Added
- Initial single-page website launch
- Hero section with animated breathing text
- Sacred Reciprocity flow diagram
- Six Gift Circles:
  - Wisdom Circle
  - Creativity Circle
  - Healing Circle
  - Service Circle
  - Abundance Circle
  - Sacred Tech Circle
- Community features section
- Sacred Economics philosophy section
- Email signup form via Formspree
- Ko-fi donation widget
- Floating heart animations
- Smooth scroll navigation
- Responsive design for mobile/desktop
- Custom domain (infin.love)
- GitHub Pages hosting
- Purple/pink gradient design aesthetic

---

## Version History Summary

- **v1.0.0** (2025-01-14): Production-ready release with full accessibility, PWA support, community health files, and automation
- **v0.1.0** (2025-01-01): Initial launch with core functionality

---

## How to Read This Changelog

### Change Categories:
- **Added**: New features or files
- **Changed**: Changes to existing functionality
- **Deprecated**: Soon-to-be removed features
- **Removed**: Removed features
- **Fixed**: Bug fixes
- **Security**: Security improvements
- **Improved**: Enhancements to existing features

### Semantic Versioning:
- **MAJOR** (X.0.0): Incompatible changes or complete redesigns
- **MINOR** (0.X.0): New features added in backwards-compatible manner
- **PATCH** (0.0.X): Backwards-compatible bug fixes

---

[Unreleased]: https://github.com/Luminous-Dynamics/infin-love/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/Luminous-Dynamics/infin-love/compare/v0.1.0...v1.0.0
[0.1.0]: https://github.com/Luminous-Dynamics/infin-love/releases/tag/v0.1.0
