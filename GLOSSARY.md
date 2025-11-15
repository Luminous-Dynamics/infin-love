# Glossary 📖

> *Definitions of terms used in Infin.Love documentation and community.*

---

## How to Use This Glossary

This glossary defines terms you'll encounter in Infin.Love. Terms are organized by category for easy reference.

**Categories:**
- [Gift Economy & Values](#gift-economy--values)
- [Technical Terms](#technical-terms)
- [Development & Contributing](#development--contributing)
- [Community & Governance](#community--governance)
- [Web Standards & Accessibility](#web-standards--accessibility)
- [Automation & CI/CD](#automation--cicd)

---

## Gift Economy & Values

### Sacred Reciprocity
The practice of giving and receiving as one unified flow, rather than separate transactions. Based on trust, abundance, and relationship rather than obligation, scarcity, and exchange.

**Related:** Gift Economy, Sacred Economics

### Gift Economy
An economic system based on freely giving goods/services without explicit agreement for immediate or future compensation. Contrasts with barter or market economy.

**Example:** Open source software, Infin.Love project

### Sacred Economics
An approach to economics that recognizes the sacred dimension of giving, receiving, and human relationship. Money and resources are treated as sacred trust, not private property to hoard.

**Source:** Charles Eisenstein's work

### Gift Circle
A group of people practicing sacred reciprocity by freely giving and receiving within a defined community. Can be local (in-person) or virtual.

**Example:** The Infin.Love contributor community

### Sacred Commons
Our custom open-source license that balances freedom with values. Allows free use, modification, and commercial application while honoring source and encouraging reciprocity.

**See:** [LICENSE](LICENSE)

### Abundance Mindset
Worldview that sees resources and goodness as abundant rather than scarce. Contrasts with scarcity mindset.

**In practice:** "There's enough for everyone" vs. "I need to hoard my fair share"

### Pass Forward
The practice of receiving a gift and later giving to others (not necessarily the same person). Completes the circle of reciprocity.

**Example:** You receive help, you later help someone else

### Scorekeeping
Tracking who gave what to whom to ensure "fairness." Discouraged in gift economy because it creates obligation and kills relationship.

**We don't do this!**

---

## Technical Terms

### Progressive Web App (PWA)
A website that can be installed on devices like a mobile app, works offline, and provides app-like experience while remaining web-based.

**Infin.Love:** Has manifest.json for PWA capability

### Single-Page Application (SPA)
A website with all content on one page, using smooth scrolling or JavaScript to show different sections without page reloads.

**Infin.Love:** Uses smooth scrolling SPA pattern

### Semantic HTML
HTML that uses meaningful element names (like `<article>`, `<nav>`, `<main>`) rather than generic ones (like `<div>`, `<span>`). Improves accessibility and SEO.

**Example:** `<nav>` for navigation, `<article>` for content

### Content Security Policy (CSP)
Security feature that restricts where resources (scripts, styles, images) can be loaded from. Prevents many types of attacks.

**Infin.Love:** Has strict CSP in index.html

### Responsive Design
Web design that adapts to different screen sizes (mobile, tablet, desktop) rather than having separate sites for each.

**Method:** CSS media queries, flexible layouts

### Mobile-First Design
Designing for mobile devices first, then enhancing for larger screens. Often results in simpler, faster designs.

**Infin.Love:** Uses mobile-first approach

---

## Development & Contributing

### Fork
Creating your own copy of a repository on GitHub. Allows you to experiment and make changes without affecting the original.

**Workflow:** Fork → Make changes → Pull request

### Pull Request (PR)
Proposal to merge your changes back into the main repository. Allows code review before integration.

**Also called:** Merge request (in GitLab)

### Issue
A GitHub feature for tracking bugs, feature requests, questions, or tasks.

**Types:** Bug report, Feature request, Question, Good first issue

### Good First Issue
An issue labeled as suitable for newcomers. Usually has clear scope, good documentation, and mentorship available.

**Look for:** `good-first-issue` label

### Code Review
Process where maintainers/contributors review proposed changes before merging. Ensures quality and knowledge sharing.

**Tone:** Constructive, educational, kind

### Commit
A saved change to the repository with a message describing what changed and why.

**Format:** `type: description` (e.g., "fix: improve mobile navigation")

### Branch
A parallel version of the repository where you can make changes without affecting the main version.

**Common:** `main` (production), `feature/your-feature` (your work)

### Merge
Combining changes from one branch into another (typically your feature branch into main).

**After:** Pull request approval and CI/CD checks passing

### Triage
The process of reviewing new issues/PRs, adding labels, setting priority, and deciding next steps.

**Done by:** Maintainers, sometimes active contributors

---

## Community & Governance

### Maintainer
Person with commit access who reviews PRs, manages issues, makes decisions, and stewards the project.

**Current:** Tristan Stoltz

**See:** [MAINTAINERS.md](MAINTAINERS.md)

### Contributor
Anyone who has contributed to the project in any way (code, docs, design, ideas, support, etc.).

**Recognition:** Listed in [CONTRIBUTORS.md](CONTRIBUTORS.md)

### Active Contributor
Contributor with sustained engagement over time (3+ contributions in 6 months). Has weighted voice in major decisions.

**Benefits:** Early access to plans, invitation to planning discussions

### Community Member
Anyone who engages with Infin.Love in any way. You're already one!

**Rights:** Ask questions, propose ideas, participate in discussions, contribute at any level

### Code of Conduct
Set of rules and expectations for community behavior. Ours is called "Sacred Covenant."

**See:** [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

### Governance
How decisions are made, who has authority, processes for resolving conflicts, and accountability mechanisms.

**See:** [GOVERNANCE.md](GOVERNANCE.md)

### Consensus
Decision-making approach where all voices are heard and decision proceeds when no one blocks (not unanimous, but no serious objections).

**Used for:** Major decisions affecting project vision/values

### Restorative Justice
Approach to conflict that focuses on repairing harm and restoring relationships, rather than punishment.

**Example:** Bringing people together to understand impact and make amends

### Stewardship
Holding responsibility for something on behalf of the community, not as owner. Maintainers are stewards.

**Mindset:** Caretaker, not boss

---

## Web Standards & Accessibility

### WCAG
Web Content Accessibility Guidelines - international standard for accessible web content.

**Levels:** A (minimum), AA (standard), AAA (enhanced)

**Infin.Love:** AA compliant

### ARIA
Accessible Rich Internet Applications - HTML attributes that improve accessibility for assistive technologies.

**Example:** `aria-label="Close menu"` on a button with just an X

### Screen Reader
Software that reads web content aloud for blind or visually impaired users.

**Examples:** NVDA (Windows), VoiceOver (Mac), JAWS (Windows)

### Keyboard Navigation
Ability to use a website entirely with keyboard (Tab, Enter, Escape, arrows) without a mouse.

**Essential for:** Blind users, motor disabilities, power users

### Focus State
Visual indication of which element is currently selected when navigating with keyboard.

**Example:** Blue outline around a button when tabbed to

### Skip Link
Hidden link that becomes visible when focused, allowing keyboard users to skip repetitive navigation and jump to main content.

**Infin.Love:** Has "Skip to content" link

### Alt Text
Text description of an image that screen readers speak aloud and displays if image fails to load.

**Example:** `alt="Pink gradient with floating hearts"`

### Semantic Landmark
HTML elements (`<header>`, `<nav>`, `<main>`, `<footer>`) that help screen reader users navigate page structure.

**Analogy:** Chapters in a book

### Color Contrast
Ratio between foreground (text) and background colors. Higher ratio = easier to read.

**WCAG AA:** 4.5:1 for normal text, 3:1 for large text

---

## Automation & CI/CD

### CI/CD
Continuous Integration / Continuous Deployment - automated testing and deployment of code changes.

**Infin.Love:** 7 GitHub Actions workflows

### GitHub Actions
GitHub's built-in CI/CD tool that runs automated workflows when events occur (push, PR, schedule).

**Used for:** Testing, quality checks, deployments, automation

### Workflow
Automated process defined in YAML file that runs when triggered.

**Example:** HTML validation workflow runs on every push

### Lighthouse
Google's automated tool for testing web quality (performance, accessibility, SEO, best practices).

**Scores:** 0-100 for each category

**Infin.Love:** 95+ all categories

### Build Process
Steps to transform source code into deployable code (compile, bundle, optimize).

**Infin.Love:** None! Pure HTML/CSS/JS means no build needed

### Deployment
Process of publishing code changes to production (making them live).

**Infin.Love:** Automatic via GitHub Pages when pushed to main

### Dependabot
GitHub's automated tool that checks for dependency updates and creates PRs to update them.

**Monitors:** npm packages, GitHub Actions

### Labeler
Automation that automatically adds labels to PRs based on which files are changed.

**Infin.Love:** Labels by file type and PR size

### Stale Bot
Automation that marks old, inactive issues/PRs as stale and eventually closes them if no activity.

**Purpose:** Keeps backlog manageable and relevant

---

## Project-Specific Terms

### Infin.Love
The name of this project. Play on "infinite love" - love that multiplies when shared.

**Pronunciation:** "Infinite Love" (the period is silent)

### Luminous Dynamics
Parent organization that created and maintains Infin.Love.

**Website:** https://luminousdynamics.org

### Evolving Resonant Cocreationism (ERC)
Philosophical foundation underlying Infin.Love and Luminous Dynamics.

**Website:** https://evolvingresonantcocreationism.com

### Sacred Tech Circle
One of the six gift circles on Infin.Love - focused on building conscious technology together.

**Example:** This open-source project

### Ko-fi
Platform used for voluntary financial support. Not required, only if genuinely moved to give.

**Link:** https://ko-fi.com/luminousdynamics

### Formspree
Service that handles form submissions (email collection) without backend code.

**Used for:** Newsletter signup on Infin.Love

---

## Development Tools & Platforms

### GitHub Pages
Free static site hosting provided by GitHub. Automatically deploys from repository.

**Infin.Love:** Hosted at https://infin.love via GitHub Pages

### Git
Version control system that tracks changes to code over time.

**Not:** GitHub (Git is the tool, GitHub is the hosting platform)

### Repository (Repo)
A project stored in Git, containing code, files, and full history.

**Infin.Love:** https://github.com/Luminous-Dynamics/infin-love

### Markdown
Lightweight markup language for formatting text (like this glossary).

**File extension:** `.md`

**Syntax:** `**bold**`, `*italic*`, `[link](url)`, `# Heading`

### YAML
Human-readable data format used for configuration files.

**File extension:** `.yml` or `.yaml`

**Used in:** GitHub Actions workflows, issue templates

### JSON
JavaScript Object Notation - data format for structured information.

**File extension:** `.json`

**Example:** `manifest.json` (PWA config)

---

## License & Legal

### Open Source
Software where source code is publicly available and can be freely used, modified, and distributed.

**Infin.Love:** Open source under Sacred Commons License

### Attribution
Giving credit to original creators when using their work.

**Sacred Commons:** Appreciated but not legally required

### Fork (license context)
Creating a derivative project based on original. Allowed under Sacred Commons with attribution.

**Different from:** Git fork (copy of repository)

### Proprietary
Software where source code is secret and use is restricted.

**Opposite of:** Open source

**Infin.Love:** Not proprietary - completely open!

---

## SEO & Web Standards

### SEO
Search Engine Optimization - making websites more discoverable in search engines like Google.

**Techniques:** Good content, meta tags, sitemap, fast loading, accessibility

### Open Graph
Protocol for controlling how content appears when shared on social media.

**Tags:** `og:title`, `og:description`, `og:image`

### Sitemap
XML file listing all pages on a website to help search engines index them.

**Infin.Love:** Has sitemap.xml

### robots.txt
File telling search engine crawlers which pages to index or skip.

**Infin.Love:** Allows all, points to sitemap

### Canonical URL
The "official" version of a page when duplicate/similar pages exist.

**Prevents:** Search engines treating duplicates as separate pages

---

## Performance Terms

### Page Load Time
How long until a page is fully loaded and interactive.

**Infin.Love:** ~0.8 seconds

### First Contentful Paint (FCP)
How long until first piece of content appears on screen.

**Target:** <1.8 seconds

### Largest Contentful Paint (LCP)
How long until main content is visible.

**Target:** <2.5 seconds

### Cumulative Layout Shift (CLS)
Measure of unexpected layout changes as page loads. Lower is better.

**Target:** <0.1

### Core Web Vitals
Google's metrics for user experience: LCP, FID (First Input Delay), CLS.

**Infin.Love:** Excellent scores on all

---

## Community Participation Terms

### Lurking
Reading/observing community without actively participating. Totally fine!

**Also called:** Passive participation

### Drive-by Contribution
One-time contribution from someone who doesn't become regular contributor.

**Status:** Welcomed and appreciated!

### Burnout
Physical/emotional exhaustion from overwork or stress. Major concern for maintainers.

**Prevention:** See [MAINTAINERS.md](MAINTAINERS.md)

### Scope Creep
When project or feature gradually expands beyond original vision.

**Management:** Clear roadmap, say "no" to off-mission features

### Bikeshedding
Spending disproportionate time on trivial decisions (like what color to paint a bikeshed).

**Avoid by:** Focus on high-impact decisions, defer minor ones

---

## Want to Add a Term?

**This glossary is a living document!**

If you encounter a term that's not defined here:

1. Ask about it in [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
2. Once clarified, suggest adding it to this glossary
3. Or submit a PR adding it yourself!

Your questions help future contributors.

---

## Related Documents

- [FAQ.md](FAQ.md) - Frequently asked questions
- [ONBOARDING.md](ONBOARDING.md) - New contributor guide
- [CONTRIBUTING.md](CONTRIBUTING.md) - How to contribute
- [VISION.md](VISION.md) - Project philosophy
- [GOVERNANCE.md](GOVERNANCE.md) - How decisions are made

---

<div align="center">

**Language is power. Shared understanding is sacred.** 💜

*Thank you for learning with us!*

---

**Last updated:** January 2025

**[⬆ Back to Top](#glossary-)**

</div>
