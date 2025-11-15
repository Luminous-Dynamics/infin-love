# Quick Start Guide ⚡

> *Get contributing in 5 minutes. Everything you need, nothing you don't.*

---

## 🚀 First Contribution in 5 Steps

```bash
# 1. Fork & Clone
git clone https://github.com/YOUR-USERNAME/infin-love.git
cd infin-love

# 2. Create Branch
git checkout -b fix/your-fix-name

# 3. Make Changes
# Edit index.html (or other files)
# Open index.html in browser to test

# 4. Commit
git add .
git commit -m "fix: description of what you fixed"

# 5. Push & PR
git push origin fix/your-fix-name
# Open PR on GitHub
```

**That's it!** You're a contributor. 🎉

---

## 📚 Essential Links

| What | Where |
|------|-------|
| **Full Guide** | [ONBOARDING.md](ONBOARDING.md) |
| **Questions** | [FAQ.md](FAQ.md) |
| **How to Contribute** | [CONTRIBUTING.md](CONTRIBUTING.md) |
| **Discuss** | [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions) |
| **Report Bug** | [New Issue](https://github.com/Luminous-Dynamics/infin-love/issues/new?template=bug_report.yml) |
| **Suggest Feature** | [New Discussion](https://github.com/Luminous-Dynamics/infin-love/discussions/new?category=ideas) |

---

## 🔧 Common Commands

### Development
```bash
# No build needed! Just open in browser:
open index.html

# Or use local server:
python -m http.server 8000
# Then visit: http://localhost:8000
```

### Git Workflow
```bash
# Update your fork
git fetch origin
git merge origin/main

# Create feature branch
git checkout -b feature/my-feature

# Stage all changes
git add .

# Commit with message
git commit -m "feat: add new feature"

# Push to your fork
git push origin feature/my-feature
```

### Commit Message Format
```
type: brief description (50 chars max)

- Detailed point 1
- Detailed point 2

Fixes #123
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

---

## ✅ Before Submitting PR

- [ ] Code works (tested in browser)
- [ ] Mobile looks good (DevTools → Device mode)
- [ ] Keyboard navigation works (Tab through page)
- [ ] No console errors (F12 → Console)
- [ ] Commit message follows format
- [ ] Branch is up to date with main

---

## 🧪 Testing Checklist

**Quick Test (2 minutes):**
- [ ] Open `index.html` in browser
- [ ] Click all navigation links
- [ ] Test mobile menu (resize window)
- [ ] Check console for errors (F12)

**Full Test (10 minutes):**
- [ ] Test on mobile device (or DevTools)
- [ ] Tab through entire page (keyboard only)
- [ ] Test form submission
- [ ] Check all external links work
- [ ] View on different browser

---

## 🏷️ Finding Issues to Work On

| Label | Meaning | Good For |
|-------|---------|----------|
| `good-first-issue` | Beginner-friendly | First-timers |
| `help-wanted` | Needs contributors | Everyone |
| `priority: high` | Important | Experienced |
| `effort: small` | < 2 hours | Quick wins |

**Browse:** [Good First Issues](https://github.com/Luminous-Dynamics/infin-love/labels/good-first-issue)

---

## 🎨 Design System Quick Reference

### Colors
```css
--primary-color: #E91E63      /* Pink */
--primary-light: #F06292      /* Light pink */
--text-primary: #212121       /* Dark gray */
--text-light: #FFFFFF         /* White */
```

### Spacing
```css
--space-4: 1rem     /* 16px - standard */
--space-6: 1.5rem   /* 24px - sections */
--space-8: 2rem     /* 32px - large gaps */
```

### Typography
```css
--font-size-md: 1rem        /* 16px - body */
--font-size-2xl: 1.5rem     /* 24px - subheadings */
--font-size-4xl: 2.5rem     /* 40px - headings */
```

**Full system:** [DESIGN.md](DESIGN.md)

---

## 🐛 Debugging Tips

**Page not loading?**
- Check browser console (F12)
- Look for JavaScript errors
- Verify file paths are correct

**Styles not applying?**
- Clear browser cache (Ctrl+Shift+Del)
- Check CSS syntax
- Verify selector specificity

**Animations jerky?**
- Limit to `transform` and `opacity`
- Use `will-change` sparingly
- Check frame rate in DevTools

---

## 📝 Documentation Structure

```
infin-love/
├── README.md          ← Start here
├── QUICK_START.md     ← You are here!
├── ONBOARDING.md      ← Full contributor guide
├── CONTRIBUTING.md    ← Detailed contribution process
├── FAQ.md             ← Common questions
├── GLOSSARY.md        ← Term definitions
├── CODE_OF_CONDUCT.md ← Community standards
├── DESIGN.md          ← Design system
├── TESTING.md         ← Testing procedures
└── ...more
```

---

## 💬 Getting Help

**Stuck?** Ask questions! No question is stupid.

1. **Check [FAQ.md](FAQ.md)** - Might be answered already
2. **Search [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)** - Others may have asked
3. **Ask in [Discussions Q&A](https://github.com/Luminous-Dynamics/infin-love/discussions/categories/q-a)** - Community will help
4. **Email:** tristan.stoltz@gmail.com (private matters only)

**Response time:** 2-3 days for maintainers, often faster from community

---

## 🌟 Pro Tips

**Speed up development:**
- Use browser DevTools Console for quick JS testing
- Learn keyboard shortcuts (Ctrl+Shift+M for mobile view)
- Install EditorConfig plugin for consistent formatting

**Improve your PRs:**
- Keep changes focused (one issue per PR)
- Test thoroughly before submitting
- Write clear commit messages
- Respond quickly to review feedback

**Level up:**
- Review others' PRs (learn by reading code)
- Help answer questions in Discussions
- Write documentation improvements
- Share your learnings

---

## 🎁 Ways to Contribute (Besides Code)

- 📖 Fix typos in documentation
- 🎨 Suggest design improvements
- 🐛 Report bugs you find
- 💡 Propose feature ideas
- ❓ Answer questions in Discussions
- 📣 Share project on social media
- ⭐ Star the repository
- 💜 Send encouragement to maintainers

**All gifts valued equally!**

---

## ⏱️ Time Estimates

| Task | Time |
|------|------|
| First contribution setup | 15 min |
| Simple typo fix | 5 min |
| Documentation improvement | 30 min |
| Small bug fix | 1-2 hours |
| New feature | 4-8 hours |
| Full testing suite | 1 hour |

*Your mileage may vary!*

---

## 🔐 Security

**Found a security issue?**
- ⚠️ **DO NOT** open a public issue
- ✅ Email: tristan.stoltz@gmail.com
- Subject: "Security Vulnerability"
- Include details privately

See [SECURITY.md](SECURITY.md) for full policy.

---

## 🎉 After Your PR is Merged

**You'll be:**
- ✅ Listed in [CONTRIBUTORS.md](CONTRIBUTORS.md)
- ✅ Credited in release notes
- ✅ Part of the community forever!

**Next steps:**
- Pick another issue
- Help review other PRs
- Welcome new contributors
- Spread the love 💜

---

## 📋 Cheat Sheet Summary

```bash
# Clone
git clone https://github.com/YOUR-USERNAME/infin-love.git

# Branch
git checkout -b type/description

# Commit
git commit -m "type: description"

# Push
git push origin type/description

# Test
open index.html  # No build needed!
```

**Labels:** `good-first-issue`, `help-wanted`, `effort: small`

**Resources:** [ONBOARDING.md](ONBOARDING.md) | [FAQ.md](FAQ.md) | [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)

**Help:** Ask in Discussions or email tristan.stoltz@gmail.com

---

<div align="center">

**Ready? Let's go! 🚀**

*Every journey starts with a single commit.*

**You've got this!** 💜

---

**Quick links:** [Full Guide](ONBOARDING.md) • [FAQ](FAQ.md) • [Contribute](CONTRIBUTING.md) • [Discuss](https://github.com/Luminous-Dynamics/infin-love/discussions)

</div>
