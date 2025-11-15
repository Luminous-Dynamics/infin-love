# Troubleshooting Guide 🔧

> *Solutions to common problems - get back to creating!*

This guide helps you quickly resolve common issues when contributing to Infin.Love. If you don't find your answer here, check [FAQ.md](FAQ.md) or ask in [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions).

**Quick Navigation:**
- [Git & GitHub Issues](#git--github-issues)
- [Development Issues](#development-issues)
- [Build & CI/CD Issues](#build--cicd-issues)
- [Testing Issues](#testing-issues)
- [Contributing Issues](#contributing-issues)
- [Getting Help](#getting-help)

---

## Git & GitHub Issues

### 🔴 Problem: "Permission denied" when pushing

**Symptoms:**
```bash
remote: Permission to Luminous-Dynamics/infin-love.git denied
fatal: unable to access 'https://github.com/Luminous-Dynamics/infin-love.git/': The requested URL returned error: 403
```

**Solution:**
You're trying to push directly to the main repository. You need to:

1. **Fork the repository first:**
   - Go to https://github.com/Luminous-Dynamics/infin-love
   - Click "Fork" button (top right)

2. **Clone YOUR fork:**
   ```bash
   git clone https://github.com/YOUR-USERNAME/infin-love.git
   ```

3. **Push to your fork:**
   ```bash
   git push origin your-branch-name
   ```

4. **Create a Pull Request from your fork to the main repository**

### 🔴 Problem: Merge conflicts

**Symptoms:**
```bash
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

**Solution:**

1. **See which files have conflicts:**
   ```bash
   git status
   ```

2. **Open the conflicted file** - Look for conflict markers:
   ```html
   <<<<<<< HEAD
   Your changes
   =======
   Their changes
   >>>>>>> main
   ```

3. **Resolve the conflict:**
   - Decide which changes to keep
   - Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
   - Keep the best combination of both changes

4. **Mark as resolved:**
   ```bash
   git add index.html
   git commit -m "resolve: merge conflict in index.html"
   ```

5. **Continue the rebase/merge:**
   ```bash
   git rebase --continue
   # OR
   git merge --continue
   ```

**Prevention:**
- Keep your branch up to date with main:
  ```bash
  git fetch origin
  git rebase origin/main
  ```

### 🔴 Problem: "Detached HEAD" state

**Symptoms:**
```bash
You are in 'detached HEAD' state.
```

**Solution:**

1. **If you want to save your work:**
   ```bash
   git checkout -b my-new-branch-name
   ```

2. **If you want to discard and go back:**
   ```bash
   git checkout main
   ```

3. **To check where you are:**
   ```bash
   git branch
   git status
   ```

### 🔴 Problem: Accidentally committed to wrong branch

**Symptoms:**
- You committed to `main` instead of a feature branch
- You want to move commits to a new branch

**Solution:**

1. **Create a new branch with your commits:**
   ```bash
   git branch my-feature-branch
   ```

2. **Reset main to origin/main:**
   ```bash
   git checkout main
   git reset --hard origin/main
   ```

3. **Switch to your new branch:**
   ```bash
   git checkout my-feature-branch
   ```

**Note:** Only do this if you haven't pushed yet!

### 🔴 Problem: Need to undo last commit

**Symptoms:**
- Made a mistake in commit message
- Committed too early
- Want to add more changes to the commit

**Solution:**

**If you haven't pushed yet:**
```bash
# Undo commit but keep changes
git reset --soft HEAD~1

# Undo commit and changes
git reset --hard HEAD~1

# Amend the last commit
git add forgotten-file.html
git commit --amend --no-edit
```

**If you've already pushed:**
```bash
# Create a new commit that reverses the changes
git revert HEAD
git push origin your-branch
```

### 🔴 Problem: Branch is behind main

**Symptoms:**
```bash
Your branch is behind 'origin/main' by 5 commits
```

**Solution:**

1. **Update your branch:**
   ```bash
   git checkout your-branch
   git fetch origin
   git rebase origin/main
   ```

2. **If conflicts occur**, resolve them (see "Merge conflicts" above)

3. **Force push to update your PR** (safe for your own branch):
   ```bash
   git push --force-with-lease origin your-branch
   ```

### 🔴 Problem: Fork is out of date

**Symptoms:**
- Your fork's main branch is behind the upstream repository

**Solution:**

1. **Add upstream remote** (one-time setup):
   ```bash
   git remote add upstream https://github.com/Luminous-Dynamics/infin-love.git
   ```

2. **Fetch and merge:**
   ```bash
   git checkout main
   git fetch upstream
   git merge upstream/main
   git push origin main
   ```

---

## Development Issues

### 🔴 Problem: Changes not showing in browser

**Symptoms:**
- Made changes to HTML/CSS/JS
- Refresh doesn't show changes

**Solution:**

1. **Hard refresh:**
   - **Windows/Linux:** `Ctrl + F5` or `Ctrl + Shift + R`
   - **Mac:** `Cmd + Shift + R`

2. **Clear cache:**
   - Open DevTools (F12)
   - Right-click refresh button
   - Select "Empty Cache and Hard Reload"

3. **Check you're editing the right file:**
   ```bash
   # Verify file was saved
   git status

   # Check file contents
   cat index.html | grep "your change"
   ```

4. **Using a local server? Restart it:**
   ```bash
   # Stop the server (Ctrl+C)
   # Start again
   python -m http.server 8000
   ```

### 🔴 Problem: JavaScript not working

**Symptoms:**
- Console shows errors
- Interactive features broken

**Solution:**

1. **Open Browser Console:**
   - Press F12
   - Go to "Console" tab
   - Look for red error messages

2. **Common errors:**

   **"Uncaught SyntaxError"** - Missing bracket, quote, or semicolon
   ```javascript
   // ❌ Missing closing brace
   function doThing() {
       console.log('hi')

   // ✅ Fixed
   function doThing() {
       console.log('hi')
   }
   ```

   **"Uncaught ReferenceError: X is not defined"** - Variable doesn't exist
   ```javascript
   // ❌ Typo in variable name
   let myVariable = 5;
   console.log(myVarible); // Missing 'a'

   // ✅ Fixed
   let myVariable = 5;
   console.log(myVariable);
   ```

   **"Cannot read property 'X' of null"** - Element doesn't exist
   ```javascript
   // ❌ Element not found
   const button = document.getElementById('buttton'); // Typo
   button.addEventListener('click', ...); // button is null

   // ✅ Fixed with check
   const button = document.getElementById('button');
   if (button) {
       button.addEventListener('click', ...);
   }
   ```

3. **Check script order:**
   - Scripts run top-to-bottom
   - Make sure elements exist before selecting them
   - Use `DOMContentLoaded` if needed:
   ```javascript
   document.addEventListener('DOMContentLoaded', () => {
       // Your code here runs after HTML loads
   });
   ```

### 🔴 Problem: CSS not applying

**Symptoms:**
- Styles not showing
- Page looks unstyled

**Solution:**

1. **Check specificity:**
   ```css
   /* ❌ Low specificity */
   .button {
       color: red;
   }

   /* ✅ Higher specificity wins */
   #main-nav .button {
       color: blue; /* This one applies */
   }
   ```

2. **Check typos:**
   ```css
   /* ❌ Typo in property */
   color: blu;

   /* ✅ Correct */
   color: blue;
   ```

3. **Use DevTools to inspect:**
   - Right-click element → "Inspect"
   - See which styles are applied
   - Crossed-out styles are overridden

4. **Clear cached CSS:**
   - Hard refresh (see above)
   - Or add version query: `style.css?v=2`

### 🔴 Problem: Mobile view not working

**Symptoms:**
- Desktop looks fine
- Mobile is broken or not responsive

**Solution:**

1. **Test responsive design:**
   - Open DevTools (F12)
   - Click device toolbar icon (or `Ctrl + Shift + M`)
   - Select different devices

2. **Check viewport meta tag exists:**
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

3. **Check media queries:**
   ```css
   /* Mobile first approach */
   .element {
       width: 100%; /* Mobile default */
   }

   @media (min-width: 768px) {
       .element {
           width: 50%; /* Tablet and up */
       }
   }
   ```

4. **Test on actual device if possible**

### 🔴 Problem: Images not loading

**Symptoms:**
- Broken image icon
- 404 errors for images

**Solution:**

1. **Check path is correct:**
   ```html
   <!-- ❌ Wrong path -->
   <img src="/images/logo.png">

   <!-- ✅ Correct path (relative to HTML file) -->
   <img src="logo.png">
   <!-- OR if images folder exists -->
   <img src="images/logo.png">
   ```

2. **Check file actually exists:**
   ```bash
   ls -la *.png
   ls -la images/
   ```

3. **Check file name case sensitivity:**
   - `Logo.png` ≠ `logo.png` on many systems
   - Use lowercase consistently

4. **Use absolute URLs for external images:**
   ```html
   <img src="https://example.com/image.jpg">
   ```

---

## Build & CI/CD Issues

### 🔴 Problem: CI checks failing

**Symptoms:**
- Red X on pull request
- Workflow failed notifications

**Solution:**

1. **Click "Details" on the failed check** to see what failed

2. **Common failures:**

   **HTML Validation Failed:**
   - Look for the specific error
   - Often unclosed tags, missing attributes
   ```html
   <!-- ❌ Missing closing tag -->
   <div>
       <p>Text
   </div>

   <!-- ✅ Fixed -->
   <div>
       <p>Text</p>
   </div>
   ```

   **Lighthouse Failed:**
   - Check Performance, Accessibility, SEO scores
   - Click through to see specific issues
   - Ensure you haven't broken accessibility

   **Link Checker Failed:**
   - Broken links in documentation
   - Find and fix the broken link
   - Or remove if no longer needed

   **Spell Check Failed:**
   - Typo in documentation
   - Or legitimate word not in dictionary
   - Add to `.wordlist.txt` if intentional

3. **Fix locally and push again:**
   ```bash
   # Make fixes
   git add .
   git commit -m "fix: resolve CI issues"
   git push origin your-branch
   ```

### 🔴 Problem: Spell check marking valid words

**Symptoms:**
- CI spell check fails on technical terms
- Words like "Formspree", "Ko-fi", "Infin" marked as errors

**Solution:**

1. **Add words to `.wordlist.txt`:**
   ```bash
   # Edit .wordlist.txt
   echo "yourword" >> .wordlist.txt

   # Keep alphabetically sorted
   sort .wordlist.txt -o .wordlist.txt

   # Commit
   git add .wordlist.txt
   git commit -m "chore: add 'yourword' to wordlist"
   ```

2. **Guidelines for wordlist:**
   - One word per line
   - Lowercase unless proper noun
   - Alphabetically sorted
   - No duplicates

### 🔴 Problem: Workflows not running

**Symptoms:**
- No CI checks on pull request
- Workflows should run but don't

**Solution:**

1. **Check branch name:**
   - Some workflows only run on specific branches
   - Check `.github/workflows/` files for `branches:` filters

2. **Check if workflow is enabled:**
   - Go to "Actions" tab in repository
   - Check if workflows are enabled

3. **Wait a few minutes:**
   - Sometimes there's a delay
   - GitHub may be experiencing issues

4. **Check workflow syntax:**
   - YAML syntax errors prevent running
   - Look for error messages in Actions tab

---

## Testing Issues

### 🔴 Problem: Accessibility tests failing

**Symptoms:**
- Lighthouse accessibility score below 100
- WCAG violations detected

**Solution:**

1. **Common accessibility issues:**

   **Missing alt text:**
   ```html
   <!-- ❌ No alt text -->
   <img src="logo.png">

   <!-- ✅ Descriptive alt -->
   <img src="logo.png" alt="Infin.Love logo">

   <!-- ✅ Decorative image -->
   <img src="decoration.png" alt="" aria-hidden="true">
   ```

   **Low color contrast:**
   ```css
   /* ❌ Light gray on white - poor contrast */
   .text {
       color: #ccc;
       background: #fff;
   }

   /* ✅ Sufficient contrast (4.5:1 minimum for normal text) */
   .text {
       color: #666;
       background: #fff;
   }
   ```

   **Missing labels:**
   ```html
   <!-- ❌ No label -->
   <input type="text" placeholder="Name">

   <!-- ✅ Proper label -->
   <label for="name">Name</label>
   <input type="text" id="name" placeholder="Name">
   ```

2. **Test with screen reader:**
   - **Windows:** NVDA (free)
   - **Mac:** VoiceOver (built-in, Cmd+F5)
   - Navigate using Tab key
   - Ensure all content is announced properly

3. **Use Accessibility DevTools:**
   - Chrome: Lighthouse audit
   - Firefox: Accessibility Inspector
   - WAVE browser extension

### 🔴 Problem: Performance score dropped

**Symptoms:**
- Lighthouse performance below 95
- Page loading slowly

**Solution:**

1. **Check what changed:**
   - Did you add large images?
   - New external scripts?
   - Complex animations?

2. **Optimize images:**
   ```bash
   # Use compressed images
   # Keep under 100KB when possible
   # Use appropriate formats (JPEG for photos, PNG for graphics)
   ```

3. **Check JavaScript:**
   ```javascript
   // ❌ Too many animations
   setInterval(() => createHeart(), 100); // Too frequent

   // ✅ Reasonable rate
   setInterval(() => createHeartIfPossible(), 2000); // Every 2 seconds
   ```

4. **Limit concurrent animations:**
   ```javascript
   const MAX_HEARTS = 15;
   if (currentHearts < MAX_HEARTS) {
       createHeart();
   }
   ```

### 🔴 Problem: Mobile testing issues

**Symptoms:**
- Site works on desktop
- Broken on mobile devices

**Solution:**

1. **Use DevTools device mode:**
   - F12 → Device Toolbar (or Ctrl+Shift+M)
   - Test iPhone, Android, tablet sizes

2. **Check touch targets:**
   - Minimum 44x44px for tap areas
   ```css
   button {
       min-width: 44px;
       min-height: 44px;
       padding: 12px 24px;
   }
   ```

3. **Test actual device if possible:**
   - Use your phone to visit localhost
   - Find your computer's local IP:
     ```bash
     # Mac/Linux
     ifconfig | grep inet

     # Windows
     ipconfig
     ```
   - Visit `http://YOUR-IP:8000` on phone

---

## Contributing Issues

### 🔴 Problem: Don't know what to work on

**Symptoms:**
- Want to contribute but overwhelmed
- Don't know where to start

**Solution:**

1. **Start with our learning paths:**
   - [LEARNING_PATHS.md](LEARNING_PATHS.md) - Find your journey
   - Choose your skill level and path

2. **Browse good first issues:**
   - [Good First Issues](https://github.com/Luminous-Dynamics/infin-love/labels/good-first-issue)
   - Clear, beginner-friendly tasks

3. **Small contributions are valuable:**
   - Fix a typo in docs
   - Improve a comment
   - Add a word to wordlist
   - Answer a question in Discussions

4. **Ask for guidance:**
   - Comment on an issue: "I'd like to work on this"
   - Ask in Discussions: "What needs help?"

### 🔴 Problem: Confused by documentation

**Symptoms:**
- Instructions unclear
- Stuck on a step
- Don't understand terminology

**Solution:**

1. **Check our glossary:**
   - [GLOSSARY.md](GLOSSARY.md) - 100+ terms defined

2. **Read the FAQ:**
   - [FAQ.md](FAQ.md) - 80+ answered questions

3. **See practical examples:**
   - [EXAMPLES.md](EXAMPLES.md) - Code patterns with explanations

4. **Ask for help:**
   - Don't struggle alone!
   - [GitHub Discussions Q&A](https://github.com/Luminous-Dynamics/infin-love/discussions/categories/q-a)
   - We're here to help 💜

### 🔴 Problem: Pull request not getting reviewed

**Symptoms:**
- Submitted PR days ago
- No response from maintainers

**Solution:**

1. **Wait at least 3-5 days:**
   - Maintainers review in their spare time
   - Expect response within a week

2. **Check PR is complete:**
   - All CI checks passing?
   - Description filled out?
   - Draft vs. Ready for Review?

3. **Politely ping after 1 week:**
   - Comment: "Friendly ping - this is ready for review when you have time!"

4. **Make sure you followed guidelines:**
   - [CONTRIBUTING.md](CONTRIBUTING.md) - Did you follow the process?

### 🔴 Problem: PR rejected or changes requested

**Symptoms:**
- Maintainer asked for changes
- Not sure how to address feedback

**Solution:**

1. **Don't take it personally:**
   - Code review is normal and helpful
   - Every contribution is appreciated

2. **Read the feedback carefully:**
   - What specifically needs to change?
   - Why was the change requested?

3. **Ask for clarification:**
   - "Could you elaborate on X?"
   - "Do you mean I should do Y?"

4. **Make the changes:**
   ```bash
   # Make requested changes
   git add .
   git commit -m "refactor: address review feedback"
   git push origin your-branch
   ```

5. **Respond to comments:**
   - "Fixed!" or "Done ✓"
   - Mark conversations as resolved

---

## Getting Help

### When to Ask for Help

**Ask anytime you:**
- Are stuck for more than 30 minutes
- Don't understand an error message
- Need clarification on requirements
- Want to discuss an approach before coding
- Are unsure if something is a bug

**Asking helps everyone** - Your question might help others!

### Where to Get Help

1. **GitHub Discussions** (Best for general questions)
   - [Q&A Category](https://github.com/Luminous-Dynamics/infin-love/discussions/categories/q-a)
   - Search first - your question may be answered
   - Include context in your question

2. **Issue Comments** (For specific issues)
   - Comment on the issue you're working on
   - Tag maintainers if needed: @Tristan-Stoltz-ERC

3. **Pull Request Comments** (For PR-specific questions)
   - Ask questions directly in the PR
   - Request review when ready

4. **Email** (For private matters)
   - tristan.stoltz@gmail.com
   - Response within 48 hours

### How to Ask Good Questions

**Include:**
1. **What you're trying to do**
2. **What you expected to happen**
3. **What actually happened**
4. **What you've tried**
5. **Error messages** (full text, screenshots)
6. **Your environment** (OS, browser, etc.)

**Example:**

> **Title:** "Getting error when running local server"
>
> **Body:**
> I'm trying to run the site locally to test my changes.
>
> **Expected:** Site should load at localhost:8000
>
> **Actual:** Getting error: "Address already in use"
>
> **Tried:**
> - Restarted computer
> - Used different port (8001)
> - Still same error
>
> **Error:**
> ```
> OSError: [Errno 48] Address already in use
> ```
>
> **Environment:**
> - macOS 13.0
> - Python 3.9
> - Chrome 120

**Good questions get quick answers!**

---

## Quick Reference

### Most Common Issues

1. **Can't push** → Fork the repo first
2. **Changes not showing** → Hard refresh (Ctrl+F5)
3. **CI failing** → Click "Details" to see why
4. **Merge conflicts** → See [Merge Conflicts](#-problem-merge-conflicts)
5. **Not sure what to work on** → See [Good First Issues](https://github.com/Luminous-Dynamics/infin-love/labels/good-first-issue)

### Essential Commands

```bash
# Update your fork
git fetch upstream
git merge upstream/main

# Create feature branch
git checkout -b feat/your-feature

# See status
git status

# Commit changes
git add .
git commit -m "type: description"

# Push to your fork
git push origin your-branch

# Reset to last commit (undo changes)
git reset --hard HEAD

# See what changed
git diff

# Revert to specific file version
git checkout -- filename.html
```

### Helpful Links

- 📖 [QUICK_START.md](QUICK_START.md) - 5-minute guide
- 🛤️ [LEARNING_PATHS.md](LEARNING_PATHS.md) - Guided journeys
- 💻 [EXAMPLES.md](EXAMPLES.md) - Code patterns
- 📚 [FAQ.md](FAQ.md) - Frequently asked questions
- 📖 [GLOSSARY.md](GLOSSARY.md) - Term definitions
- 🤝 [CONTRIBUTING.md](CONTRIBUTING.md) - Full guidelines
- 💬 [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions) - Community support

---

## Still Stuck?

**That's okay!** Everyone gets stuck sometimes.

1. Take a break - fresh eyes help
2. Search Google/Stack Overflow for error messages
3. Ask in [Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)
4. Email tristan.stoltz@gmail.com

**Remember:** There are no stupid questions. We were all beginners once, and we're here to help you succeed. 💜

---

<div align="center">

**Don't give up!** Every expert was once a beginner who didn't quit.

**Community support:** [GitHub Discussions](https://github.com/Luminous-Dynamics/infin-love/discussions)

**Made with love** • **Here to help** • **You've got this!** 💜

[⬆ Back to Top](#troubleshooting-guide-)

</div>
