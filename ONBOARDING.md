# Welcome to Infin.Love! 💜

> *Your journey into sacred reciprocity and conscious technology starts here.*

---

## Welcome, Beautiful Soul! 🌟

Thank you for choosing to contribute to Infin.Love! Whether you're here to fix a typo, add a feature, or simply learn—you're already part of our gift circle. This guide will help you get started quickly and confidently.

**Time to first contribution**: ~15 minutes
**Skill level**: All levels welcome (we'll guide you!)

---

## Quick Start (5 Minutes) ⚡

### For First-Time Contributors

1. **Fork the repository**
   - Click the "Fork" button at the top right
   - This creates your own copy of the project

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/infin-love.git
   cd infin-love
   ```

3. **Open index.html in your browser**
   - Double-click `index.html` or
   - Right-click → Open With → Your Browser
   - That's it! No build process needed.

4. **Make a small change**
   - Try editing a word in `index.html`
   - Refresh your browser to see the change
   - Congratulations! You're developing! 🎉

### For Experienced Contributors

```bash
# Clone and setup
git clone https://github.com/YOUR-USERNAME/infin-love.git
cd infin-love

# Create feature branch
git checkout -b feature/your-feature-name

# Make changes, test locally
# No build process - just open index.html

# Commit and push
git add .
git commit -m "feat: your feature description"
git push origin feature/your-feature-name

# Open PR via GitHub UI
```

**Next**: See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed workflow.

---

## What Can You Contribute? 🎁

### For Non-Coders

**Documentation**
- Fix typos or clarify confusing sections
- Add examples to guides
- Improve README or other docs
- Translate documentation (future)

**Design**
- Suggest color improvements
- Create alternative layouts
- Design new visual assets
- Improve accessibility

**Content**
- Write blog posts about the project
- Create tutorials or videos
- Share your story with the community
- Suggest copy improvements

**Community**
- Answer questions in Discussions
- Help other contributors
- Share the project
- Organize events or circles

### For Coders

**Frontend**
- Accessibility improvements
- Browser compatibility fixes
- Performance optimizations
- New interactive features
- Mobile improvements

**DevOps**
- GitHub Actions improvements
- Testing automation
- Deployment optimization
- Monitoring and analytics

**Testing**
- Write test cases
- Cross-browser testing
- Accessibility audits
- Performance testing

---

## Your First Contribution (Step by Step) 🚀

### 1. Find Something to Work On

**Good First Issues**: Start here!
- Look for issues labeled `good-first-issue`
- These are designed for newcomers
- Clear scope, helpful context provided
- Mentorship available

**Browse Issues**
- [Bug Reports](https://github.com/Luminous-Dynamics/infin-love/labels/bug)
- [Feature Requests](https://github.com/Luminous-Dynamics/infin-love/labels/enhancement)
- [Documentation](https://github.com/Luminous-Dynamics/infin-love/labels/documentation)
- [Help Wanted](https://github.com/Luminous-Dynamics/infin-love/labels/help-wanted)

**Create Your Own**
- Found a bug? Report it!
- Have an idea? Suggest it!
- See [Issue Templates](.github/ISSUE_TEMPLATE/)

### 2. Set Up Your Environment

**Prerequisites**
- Git installed ([download](https://git-scm.com/downloads))
- A web browser (Chrome, Firefox, Safari, Edge)
- A text editor (VS Code, Sublime, Atom, or any you like)

**Optional Tools**
- GitHub CLI (`gh`) for easier PR management
- Browser DevTools for debugging
- Git GUI client (GitHub Desktop, SourceTree)

**No Build Tools Required!**
- No npm install
- No webpack
- No compilation
- Just HTML, CSS, and vanilla JavaScript

### 3. Make Your Changes

**Development Workflow**

1. **Create a branch**
   ```bash
   git checkout -b fix/issue-123-description
   # or
   git checkout -b feature/new-feature-name
   ```

2. **Make your changes**
   - Edit files in your text editor
   - Save changes
   - Refresh browser to see updates

3. **Test your changes**
   - [ ] Visual check in browser
   - [ ] Test on mobile (DevTools device mode)
   - [ ] Check accessibility (keyboard navigation)
   - [ ] Validate HTML (see [TESTING.md](TESTING.md))
   - [ ] Check console for errors (F12)

4. **Follow code style**
   - 4 spaces for indentation (HTML/CSS/JS)
   - Clear, descriptive variable names
   - Add comments for complex logic
   - Match existing code style

### 4. Submit Your Contribution

**Commit Your Changes**

```bash
# Stage your changes
git add .

# Commit with clear message
git commit -m "fix: improve mobile navigation accessibility

- Add proper ARIA labels to menu button
- Fix keyboard focus order
- Improve screen reader announcements

Fixes #123"

# Push to your fork
git push origin your-branch-name
```

**Commit Message Format**

```
type: brief description (50 chars max)

- Detailed point 1
- Detailed point 2
- Detailed point 3

Fixes #issue-number
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

**Open Pull Request**

1. Go to your fork on GitHub
2. Click "Compare & pull request"
3. Fill in the PR template
4. Explain what and why
5. Link related issues
6. Submit! 🎉

### 5. The Review Process

**What Happens Next**

1. **Automated Checks** (2-3 minutes)
   - HTML validation
   - Lighthouse CI (performance, accessibility)
   - Link checking
   - Spell checking

2. **Code Review** (1-3 days)
   - Maintainer reviews your code
   - May request changes
   - Discussion and collaboration

3. **Revisions** (if needed)
   - Make requested changes
   - Push to same branch
   - PR updates automatically

4. **Merge!** 🎉
   - PR approved and merged
   - Your contribution is live!
   - Added to CONTRIBUTORS.md

**Review Expectations**

- **First response**: Within 3 days (usually sooner)
- **Full review**: Within 1 week
- **Be patient**: Maintainers are volunteers
- **Be gracious**: Reviews help us all learn

---

## Understanding the Codebase 🗺️

### Project Structure

```
infin-love/
├── index.html              # Main website (single page)
├── 404.html               # Custom error page
├── manifest.json          # PWA configuration
├── robots.txt             # SEO crawler instructions
├── sitemap.xml            # SEO sitemap
├── humans.txt             # Team credits
│
├── .github/               # GitHub configuration
│   ├── workflows/         # CI/CD automation
│   │   ├── html-validation.yml
│   │   ├── lighthouse.yml
│   │   ├── link-checker.yml
│   │   ├── spell-check.yml
│   │   └── release.yml
│   ├── ISSUE_TEMPLATE/    # Issue templates
│   ├── pull_request_template.md
│   ├── dependabot.yml     # Dependency updates
│   ├── labels.yml         # Label configuration
│   └── CODEOWNERS         # Code review assignments
│
├── docs/                  # Documentation
│   ├── README.md          # Project overview
│   ├── CONTRIBUTING.md    # How to contribute
│   ├── CODE_OF_CONDUCT.md # Community covenant
│   ├── ARCHITECTURE.md    # Technical architecture
│   ├── DEPLOYMENT.md      # Deployment guide
│   ├── TESTING.md         # Testing procedures
│   ├── BROWSERS.md        # Browser compatibility
│   ├── VISION.md          # Project vision
│   ├── SECURITY.md        # Security policy
│   ├── SUPPORT.md         # Getting help
│   ├── CONTRIBUTORS.md    # Contributor recognition
│   ├── CHANGELOG.md       # Version history
│   ├── PROJECT_STATUS.md  # Current status
│   ├── ASSETS.md          # Visual asset guide
│   └── ONBOARDING.md      # This file!
│
└── .editorconfig          # Code style settings
```

### Key Files to Know

**index.html** (~1000 lines)
- The entire website in one file
- HTML structure, embedded CSS, embedded JavaScript
- Sections: Hero, About, Philosophy, Values, Support, Footer
- Features: Hearts animation, mobile menu, form validation

**manifest.json**
- PWA configuration
- Enables "Add to Home Screen" on mobile
- Defines app name, colors, icons

**404.html**
- Custom error page shown when page not found
- Matches site branding
- Provides navigation back to main site

### Architecture Highlights

**No Build Process**
- Pure HTML, CSS, JavaScript
- No npm, webpack, or compilation
- Easy for beginners
- Fast development cycle

**Progressive Enhancement**
- Works without JavaScript
- Enhanced with JavaScript
- Accessible to all users

**Mobile-First**
- Responsive design
- Touch-optimized
- Fast on all devices

**Accessibility-First**
- WCAG 2.1 AA compliant
- Screen reader support
- Keyboard navigation
- Clear focus indicators

See [ARCHITECTURE.md](ARCHITECTURE.md) for deep dive.

---

## Development Tips 💡

### Local Development

**Workflow**

1. Open `index.html` in browser
2. Open `index.html` in text editor
3. Edit → Save → Refresh browser
4. Repeat until perfect!

**Browser DevTools**

- **F12**: Open DevTools
- **Ctrl+Shift+C**: Inspect element
- **Ctrl+Shift+M**: Mobile device view
- **Console tab**: See JavaScript errors
- **Network tab**: Check performance
- **Lighthouse tab**: Run audits

**Testing Mobile**

1. Open DevTools (F12)
2. Click device icon (Ctrl+Shift+M)
3. Select device (iPhone, iPad, etc.)
4. Test touch interactions
5. Check different orientations

**Accessibility Testing**

1. **Keyboard Navigation**
   - Tab through all interactive elements
   - Enter/Space should activate buttons
   - Escape should close modals/menus

2. **Screen Reader**
   - Windows: NVDA (free)
   - macOS: VoiceOver (built-in)
   - Check ARIA labels make sense

3. **Color Contrast**
   - Use DevTools Lighthouse
   - Should pass WCAG AA (4.5:1)

### Common Tasks

**Add a new section to the page**

1. Find the section in index.html
2. Copy existing section structure
3. Modify content
4. Update navigation links
5. Test keyboard navigation
6. Check mobile view

**Fix a bug**

1. Reproduce the bug
2. Check console for errors (F12)
3. Identify the cause
4. Make minimal fix
5. Test that bug is fixed
6. Test that nothing else broke

**Improve accessibility**

1. Run Lighthouse audit (F12 → Lighthouse)
2. Review accessibility score and issues
3. Fix reported issues
4. Test with keyboard only
5. Test with screen reader
6. Re-run Lighthouse to verify

**Optimize performance**

1. Run Lighthouse performance audit
2. Check Network tab for slow resources
3. Optimize images (compress, resize)
4. Minimize JavaScript execution
5. Check animation performance (60fps)
6. Re-run Lighthouse to verify

### Code Style Guide

**HTML**
```html
<!-- Use semantic elements -->
<main id="main-content">
  <section aria-labelledby="about-heading">
    <h2 id="about-heading">About</h2>
    <!-- Content -->
  </section>
</main>

<!-- Use ARIA labels for accessibility -->
<button aria-label="Close menu" aria-expanded="false">
  <span aria-hidden="true">✕</span>
</button>

<!-- 4-space indentation -->
<div>
    <p>Content here</p>
</div>
```

**CSS**
```css
/* Use CSS variables for consistency */
:root {
    --primary-color: #E91E63;
    --secondary-color: #F06292;
}

/* Clear selectors and comments */
.hero {
    /* Gradient background with fallback */
    background: var(--primary-color);
    background: linear-gradient(135deg, ...);
}

/* Mobile-first, then enhance */
.container {
    width: 100%;
}

@media (min-width: 768px) {
    .container {
        max-width: 1200px;
    }
}
```

**JavaScript**
```javascript
// Use modern ES6+ syntax
const button = document.querySelector('#menu-toggle');

// Add comments for complex logic
button.addEventListener('click', () => {
    // Toggle ARIA state for accessibility
    const expanded = button.getAttribute('aria-expanded') === 'true';
    button.setAttribute('aria-expanded', !expanded);
});

// Use descriptive variable names
const maxVisibleHearts = 15;
const heartAnimationDuration = 8000; // milliseconds
```

---

## Getting Help 🤝

### Where to Ask Questions

**GitHub Discussions** (Recommended)
- Ask questions about the project
- Discuss feature ideas
- Share your experience
- Get help from community

**GitHub Issues**
- Report bugs
- Request features
- Ask technical questions
- Use issue templates

**Direct Contact**
- Email: tristan.stoltz@gmail.com
- For sensitive questions only
- Response time: 1-3 days

### Before Asking

1. **Search existing issues/discussions**
   - Your question may be answered already
   - Saves everyone time

2. **Read the docs**
   - [README.md](README.md) - Project overview
   - [CONTRIBUTING.md](CONTRIBUTING.md) - Contribution guide
   - [TESTING.md](TESTING.md) - Testing guide
   - [ARCHITECTURE.md](ARCHITECTURE.md) - Technical details

3. **Try to solve it yourself**
   - Great learning opportunity
   - Check browser console for errors
   - Use DevTools to debug

4. **Prepare your question**
   - What are you trying to do?
   - What have you tried?
   - What error messages do you see?
   - Screenshots or code examples help!

### How to Ask Good Questions

**Instead of:**
> "It's broken, help!"

**Try:**
> "I'm trying to add a new section to index.html, but when I save and refresh, the styling isn't applied. I checked the browser console and see this error: [error message]. I've tried [what you tried]. Here's my code: [code snippet]. Any ideas?"

**Include:**
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Error messages (if any)
- Browser and OS version
- Code snippet or screenshot

---

## Community Culture 💜

### Our Values

**Sacred Reciprocity**
- Contributions are gifts, not transactions
- All contributions valued equally
- Help freely given and received
- Gratitude over obligation

**Radical Inclusion**
- All skill levels welcome
- No "stupid questions"
- We're all learning together
- Diversity strengthens us

**Love as Foundation**
- Kind and patient communication
- Assume good intent
- Supportive feedback
- Celebrate each other

**Conscious Technology**
- Technology as sacred practice
- Mindful of impact
- Accessibility is essential
- Privacy and ethics matter

### Expected Behavior

**Do:**
- Be kind and patient
- Welcome newcomers warmly
- Give constructive feedback
- Celebrate contributions
- Help each other learn
- Ask questions freely
- Share knowledge generously
- Credit others' work
- Respect different perspectives
- Assume good intentions

**Don't:**
- Be rude or dismissive
- Make people feel stupid
- Gatekeep or be elitist
- Demand immediate responses
- Take credit for others' work
- Harass or discriminate
- Share private information
- Spam or self-promote excessively

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for full covenant.

---

## Recognition & Appreciation 🌟

### How We Recognize Contributors

**CONTRIBUTORS.md**
- All contributors listed
- Multiple contribution types recognized
- Not just code—docs, design, support, etc.
- Gift economy-based recognition

**GitHub Profile**
- Contributions show on your GitHub profile
- Build your portfolio
- Show your values alignment

**Release Notes**
- Contributors thanked in release notes
- PR comments when changes go live
- Community-wide appreciation

**Community Gratitude**
- Genuine thanks, not just automated
- Recognition in discussions
- Peer appreciation encouraged

### Types of Contributions Recognized

- 💻 Code contributions
- 📖 Documentation improvements
- 🎨 Design and UX
- 🐛 Bug reports
- 💡 Ideas and suggestions
- 🤔 Answering questions
- 👀 Code review
- 🧪 Testing
- 🌐 Translation (future)
- 📣 Spreading the word
- 💰 Financial support
- 🙏 Spiritual support

**Everyone is valued.** Your contribution matters, no matter how small it seems.

---

## Learning Resources 📚

### For Beginners

**Git & GitHub**
- [GitHub's Git Guide](https://github.com/git-guides)
- [First Contributions](https://github.com/firstcontributions/first-contributions)
- [GitHub Learning Lab](https://lab.github.com/)

**HTML & CSS**
- [MDN HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML)
- [MDN CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/CSS)
- [CSS Tricks](https://css-tricks.com/)

**JavaScript**
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [JavaScript.info](https://javascript.info/)
- [Eloquent JavaScript (free book)](https://eloquentjavascript.net/)

**Accessibility**
- [WebAIM](https://webaim.org/)
- [A11y Project](https://www.a11yproject.com/)
- [WCAG Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/)

### Project-Specific Docs

- [ARCHITECTURE.md](ARCHITECTURE.md) - Technical deep dive
- [TESTING.md](TESTING.md) - How to test
- [BROWSERS.md](BROWSERS.md) - Browser compatibility
- [DEPLOYMENT.md](DEPLOYMENT.md) - How deployment works
- [VISION.md](VISION.md) - Project philosophy and future

---

## Next Steps 🚀

### 1. Join the Community

- ⭐ Star the repository
- 👀 Watch for updates
- 💬 Introduce yourself in Discussions
- 🐛 Browse open issues

### 2. Make Your First Contribution

- Look for `good-first-issue` label
- Or try a documentation improvement
- Follow the workflow above
- Ask questions if stuck!

### 3. Keep Contributing

- Help answer questions
- Review pull requests
- Suggest improvements
- Share with others

### 4. Grow With Us

- Learn new skills
- Build your portfolio
- Connect with community
- Make a difference

---

## Frequently Asked Questions ❓

<details>
<summary><strong>I'm not a developer. Can I still contribute?</strong></summary>

Absolutely! We value all types of contributions:
- Documentation improvements
- Bug reports and testing
- Design suggestions
- Community support
- Spreading the word
- Financial support via Ko-fi

Everyone has unique gifts to share!
</details>

<details>
<summary><strong>How long does it take to get a PR reviewed?</strong></summary>

- **First response**: Usually within 3 days
- **Full review**: Within 1 week
- **Merge time**: Depends on complexity and changes requested

Maintainers are volunteers, so please be patient. We appreciate you!
</details>

<details>
<summary><strong>What if my PR gets rejected?</strong></summary>

First, this is rare and always done respectfully. If it happens:
1. Don't take it personally
2. Ask for clarification on why
3. Learn from the feedback
4. Try a different approach
5. Start with smaller changes

Rejection is not failure—it's part of the collaborative process.
</details>

<details>
<summary><strong>Do I need to know the entire codebase?</strong></summary>

Not at all! Start small:
- Fix a typo in documentation
- Improve a comment
- Add one ARIA label
- Report a bug you found

You'll learn the codebase over time, one contribution at a time.
</details>

<details>
<summary><strong>Can I work on something not in the issues?</strong></summary>

Yes! If you have an idea:
1. Check if an issue already exists
2. If not, create a new issue first
3. Discuss your idea with maintainers
4. Get feedback before investing time
5. Then make your PR

This prevents duplicate work and ensures alignment with project goals.
</details>

<details>
<summary><strong>What if I start something but can't finish?</strong></summary>

That's totally okay! Life happens. Just:
1. Comment on the issue
2. Let us know you need to step back
3. Someone else can pick it up
4. Or come back to it later

No pressure, no obligation. It's a gift, not a contract.
</details>

<details>
<summary><strong>How do I stay updated on the project?</strong></summary>

- Watch the repository (GitHub notifications)
- Star it to bookmark
- Check Discussions regularly
- Read CHANGELOG.md for updates
- Follow releases on GitHub
</details>

<details>
<summary><strong>Is there a roadmap?</strong></summary>

Yes! See:
- [VISION.md](VISION.md) for long-term vision
- [ROADMAP.md](ROADMAP.md) for planned features
- GitHub Issues for current work
- GitHub Projects for organization

The roadmap is a living document—your input shapes it!
</details>

---

## Thank You! 🙏

Thank you for taking the time to read this guide and for considering contributing to Infin.Love. Whether this is your first open-source contribution or your thousandth, you are welcome here.

Your presence in this community is a gift. Your contributions—no matter how small they seem—make a real difference. Together, we're building more than a website; we're building a more loving, reciprocal way of relating through technology.

**Welcome to the circle.** 💜

---

## Quick Reference

**Essential Commands**
```bash
# Setup
git clone https://github.com/YOUR-USERNAME/infin-love.git
cd infin-love

# Create branch
git checkout -b feature/your-feature

# Commit
git add .
git commit -m "type: description"

# Push
git push origin feature/your-feature
```

**Essential Links**
- **Repository**: https://github.com/Luminous-Dynamics/infin-love
- **Issues**: https://github.com/Luminous-Dynamics/infin-love/issues
- **Discussions**: https://github.com/Luminous-Dynamics/infin-love/discussions
- **Live Site**: https://infin.love

**Essential Docs**
- [README.md](README.md) - Start here
- [CONTRIBUTING.md](CONTRIBUTING.md) - Contribution guidelines
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) - Community covenant
- [TESTING.md](TESTING.md) - How to test

**Need Help?**
- 💬 [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
- 📧 tristan.stoltz@gmail.com
- 📖 [SUPPORT.md](SUPPORT.md)

---

<div align="center">

**From our hearts to yours** 💜

*Every contribution is a gift. Every contributor is valued.*

*Welcome home.*

</div>
