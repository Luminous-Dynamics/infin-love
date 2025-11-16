# Quick Reference 🎯

> *Essential cheat sheets for common tasks*

Quick access to the most frequently needed commands, workflows, and information. Perfect for bookmarking!

**See also:** [QUICK_START.md](QUICK_START.md) • [EXAMPLES.md](EXAMPLES.md) • [TROUBLESHOOTING.md](TROUBLESHOOTING.md)

---

## Table of Contents

- [Git Workflow Commands](#git-workflow-commands)
- [Testing Quick Checklist](#testing-quick-checklist)
- [File Locations](#file-locations)
- [Documentation Update Workflow](#documentation-update-workflow)
- [PR Submission Checklist](#pr-submission-checklist)
- [Markdown Syntax](#markdown-syntax)
- [Common Issues & Quick Fixes](#common-issues--quick-fixes)

---

## Git Workflow Commands

### Initial Setup

```bash
# Fork repository on GitHub, then:
git clone https://github.com/YOUR-USERNAME/infin-love.git
cd infin-love
git remote add upstream https://github.com/Luminous-Dynamics/infin-love.git
```

### Daily Workflow

```bash
# Start new feature
git checkout main
git pull upstream main
git checkout -b feature/your-feature-name

# Make changes, then:
git add .
git commit -m "feat: descriptive message"

# Push to your fork
git push origin feature/your-feature-name

# Create PR on GitHub
```

### Keeping Fork Updated

```bash
git checkout main
git pull upstream main
git push origin main
```

### Fixing Mistakes

```bash
# Undo last commit (keep changes)
git reset --soft HEAD~1

# Discard local changes
git checkout -- filename.html

# Update last commit message
git commit --amend -m "new message"
```

**Full details:** [TROUBLESHOOTING.md](TROUBLESHOOTING.md#git--github-issues)

---

## Testing Quick Checklist

### Before Every PR

```markdown
- [ ] HTML validates (no errors)
- [ ] No console errors
- [ ] Keyboard navigation works (Tab, Enter, Escape)
- [ ] Tested on mobile (or DevTools mobile view)
- [ ] Lighthouse scores 95+ (all categories)
- [ ] Links work
- [ ] Spell check passes
```

### Testing Commands

```bash
# Open locally
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux

# Or use local server
python -m http.server 8000
# Visit: http://localhost:8000
```

**Full guide:** [TESTING.md](TESTING.md)

---

## File Locations

### Most Used Documentation

```
📁 Root Documentation
├── README.md              # Project overview
├── CONTRIBUTING.md        # How to contribute
├── QUICK_START.md         # 5-minute start
├── EXAMPLES.md            # Code patterns
├── TROUBLESHOOTING.md     # Problem solving
└── INDEX.md               # Navigation hub

📁 Learning Resources
├── LEARNING_PATHS.md      # Guided journeys
├── ONBOARDING.md          # Complete guide
├── RESOURCES.md           # External learning
└── QUICK_REFERENCE.md     # This file

📁 GitHub Configuration (.github/)
├── CONTRIBUTION_CHECKLISTS.md  # All checklists
├── pull_request_template.md    # PR template
├── SAVED_REPLIES.md            # Response templates
└── workflows/                   # CI/CD automation
```

### Application Files

```
index.html         # Main site
404.html           # Error page
manifest.json      # PWA config
robots.txt         # SEO
sitemap.xml        # Site structure
```

**Full inventory:** [PROJECT_STATUS.md](PROJECT_STATUS.md#file-inventory)

---

## Documentation Update Workflow

### Quick Steps

```markdown
1. Edit documentation file
2. Update INDEX.md (if new file)
3. Add cross-references from related docs
4. Add new terms to .wordlist.txt
5. Run spell check (automatic on PR)
6. Submit PR
```

### Required Updates for New Docs

```markdown
**Must Update:**
- [ ] INDEX.md (add to appropriate section)
- [ ] Add cross-references in related docs
- [ ] .wordlist.txt (new terms)
- [ ] CHANGELOG.md (document addition)

**Consider Updating:**
- [ ] PROJECT_STATUS.md (if primary doc)
- [ ] README.md (if major addition)
- [ ] GLOSSARY.md (new terminology)
```

**Full workflow:** [DIAGRAMS.md](DIAGRAMS.md#documentation-contribution-flow)

---

## PR Submission Checklist

### Copy-Paste Ready Checklist

```markdown
## Pre-Submission Checklist

### Code Quality
- [ ] HTML validates (no errors)
- [ ] No console errors
- [ ] Follows existing code style
- [ ] Comments added for complex logic

### Accessibility
- [ ] Keyboard navigation works
- [ ] Tested with screen reader (if possible)
- [ ] Color contrast meets WCAG AA
- [ ] Focus states visible
- [ ] Semantic HTML used

### Testing
- [ ] Tested on mobile
- [ ] Tested in Chrome/Firefox/Safari
- [ ] Lighthouse scores 95+
- [ ] All links work

### Documentation
- [ ] Updated relevant documentation
- [ ] Updated CHANGELOG.md (if significant)
- [ ] Added terms to .wordlist.txt

### Sacred Alignment
- [ ] Maintains accessibility
- [ ] Maintains sacred aesthetic
- [ ] Aligns with gift economy values
```

**Full template:** `.github/pull_request_template.md`

---

## Markdown Syntax

### Headers

```markdown
# H1 Header
## H2 Header
### H3 Header
```

### Emphasis

```markdown
**bold text**
*italic text*
`inline code`
```

### Links

```markdown
[Link text](URL)
[Internal doc](FILENAME.md)
[Section link](#section-name)
```

### Lists

```markdown
- Unordered item
- Another item

1. Ordered item
2. Another item

- [ ] Task list item
- [x] Completed task
```

### Code Blocks

````markdown
```javascript
const code = "example";
```
````

### Tables

```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

### Blockquotes

```markdown
> Quote or emphasis
```

**Full guide:** [STYLE_GUIDE.md](STYLE_GUIDE.md#markdown-formatting)

---

## Common Issues & Quick Fixes

### "Permission denied" when pushing

**Fix:**
```bash
# You're pushing to main repo, not your fork
# Push to your fork instead:
git remote -v  # Check your remotes
git push origin branch-name  # Not upstream
```

### Merge conflicts

**Fix:**
```bash
# 1. See conflicted files
git status

# 2. Edit files, remove conflict markers:
# <<<<<<< HEAD
# Your changes
# =======
# Their changes
# >>>>>>> main

# 3. Mark resolved
git add filename
git commit
```

### HTML validation errors

**Fix:**
- Check for unclosed tags
- Verify proper nesting
- Use validator: https://validator.w3.org/

### Spell check failures

**Fix:**
```bash
# Add new terms to .wordlist.txt
# (alphabetically, one per line)
echo "newterm" >> .wordlist.txt
```

### Lighthouse score drops

**Fix:**
- Optimize images
- Defer non-critical scripts
- Check for new console errors
- Verify accessibility hasn't regressed

**Full troubleshooting:** [TROUBLESHOOTING.md](TROUBLESHOOTING.md)

---

## Quick Terminal Commands

### Navigation

```bash
pwd              # Print working directory
ls               # List files
cd dirname       # Change directory
cd ..            # Go up one level
cd ~             # Go to home directory
```

### File Operations

```bash
cat filename     # View file contents
less filename    # View file (paginated)
mkdir dirname    # Create directory
rm filename      # Delete file
cp source dest   # Copy file
mv source dest   # Move/rename file
```

### Git Status

```bash
git status       # See current state
git log          # View commit history
git diff         # See changes
git branch       # List branches
git branch -a    # List all branches (including remote)
```

---

## Keyboard Shortcuts

### Common Editor Shortcuts (VS Code)

```
Ctrl/Cmd + S     # Save
Ctrl/Cmd + Z     # Undo
Ctrl/Cmd + F     # Find
Ctrl/Cmd + H     # Find and replace
Ctrl/Cmd + /     # Toggle comment
Ctrl/Cmd + B     # Toggle sidebar
```

### Browser DevTools

```
F12              # Open DevTools
Ctrl/Cmd + Shift + C  # Inspect element
Ctrl/Cmd + Shift + M  # Toggle device toolbar (mobile view)
Ctrl/Cmd + Shift + I  # Open DevTools (alternative)
```

---

## Essential URLs

### Project

- **Live Site:** https://infin.love
- **Repository:** https://github.com/Luminous-Dynamics/infin-love
- **Discussions:** https://github.com/Luminous-Dynamics/infin-love/discussions
- **Issues:** https://github.com/Luminous-Dynamics/infin-love/issues

### Tools

- **HTML Validator:** https://validator.w3.org/
- **Mermaid Live Editor:** https://mermaid.live/
- **GitHub Skills:** https://skills.github.com/
- **Markdown Guide:** https://www.markdownguide.org/

### Learning

- **Git Book:** https://git-scm.com/book/en/v2
- **MDN Web Docs:** https://developer.mozilla.org/
- **WCAG Quick Reference:** https://www.w3.org/WAI/WCAG21/quickref/

**More resources:** [RESOURCES.md](RESOURCES.md)

---

## Commit Message Format

### Pattern

```
type: brief description

Optional longer explanation:
- What changed
- Why it changed
- Any side effects
```

### Types

```
feat:     # New feature
fix:      # Bug fix
docs:     # Documentation only
style:    # Formatting, no code change
refactor: # Code restructure, no behavior change
test:     # Adding/updating tests
chore:    # Maintenance tasks
```

### Examples

```bash
git commit -m "feat: add mobile hamburger menu"

git commit -m "fix: correct keyboard focus trap in modal"

git commit -m "docs: update CONTRIBUTING with new workflow"
```

**Full guide:** [CONTRIBUTING.md](CONTRIBUTING.md#commit-messages)

---

## File Size Limits

### Keep It Light

```
Images:     < 200KB each
Total page: < 50KB (HTML/CSS/JS combined currently ~35KB)
Documents:  No strict limit, but consider splitting if >1000 lines
```

### Optimization

```bash
# Optimize images (use tools like):
# - ImageOptim (macOS)
# - TinyPNG (web)
# - GIMP (all platforms)

# Check current size
ls -lh filename
```

---

## Accessibility Quick Checks

### Must-Haves

```markdown
- [ ] All images have alt text
- [ ] Links have descriptive text (not "click here")
- [ ] Color contrast ≥ 4.5:1
- [ ] Headings in logical order (H1 → H2 → H3)
- [ ] Forms have labels
- [ ] Buttons have accessible names
- [ ] Skip-to-content link present
```

### Quick Test

```markdown
1. Tab through page - can reach everything?
2. Use only keyboard - can use all features?
3. Zoom to 200% - still readable?
4. Turn off CSS - still makes sense?
```

**Full testing:** [TESTING.md](TESTING.md#accessibility-testing)

---

## Getting Help

### When Stuck

**1. Check Documentation:**
- [FAQ.md](FAQ.md) - Common questions
- [TROUBLESHOOTING.md](TROUBLESHOOTING.md) - Problem solving
- [INDEX.md](INDEX.md) - Find specific docs

**2. Search Existing Issues:**
- Someone may have had same problem
- Solutions often documented

**3. Ask Community:**
- [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
- Tag maintainers if needed
- Email: tristan.stoltz@gmail.com

**4. Open Issue:**
- If it's a bug or feature request
- Provide details and context
- Be patient and kind

---

## Contributing Time Estimates

### Typical Time Investments

```
Typo fix:               5-10 minutes
Documentation update:   30-60 minutes
Small code change:      1-2 hours
New feature:            3-8 hours
Major documentation:    4-10 hours
```

*These are estimates - work at your own pace!*

---

<div align="center">

**Bookmark this page for quick access** 🎯

**Still need help?** See [SUPPORT.md](SUPPORT.md)

**Ready to contribute?** Start with [QUICK_START.md](QUICK_START.md)

Built with consciousness • Shared with love • Held in sacred reciprocity 💜

[⬆ Back to Top](#quick-reference-)

</div>
