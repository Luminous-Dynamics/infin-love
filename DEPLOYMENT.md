# Deployment Guide 🚀

This guide explains how Infin.Love is deployed and how to deploy your own version.

**See also:** [QUICK_START.md](QUICK_START.md) - Getting started • [ARCHITECTURE.md](ARCHITECTURE.md) - System design • [TESTING.md](TESTING.md) - Pre-deployment testing • [DIAGRAMS.md](DIAGRAMS.md) - Deployment workflow diagrams

## Current Deployment

### Production Site

- **URL**: https://infin.love
- **Host**: GitHub Pages
- **Branch**: `main`
- **Build**: Automatic on push to main
- **SSL**: Automatic via GitHub Pages
- **CDN**: GitHub's global CDN

### How It Works

```
git push origin main
    ↓
GitHub detects push
    ↓
GitHub Actions run (validation, tests)
    ↓
If all checks pass →
    ↓
GitHub Pages deploys automatically
    ↓
Live at https://infin.love within ~1 minute
```

---

## Initial Setup (For New Deployments)

### 1. Fork or Clone Repository

```bash
# Fork on GitHub, then clone your fork
git clone https://github.com/YOUR-USERNAME/infin-love.git
cd infin-love
```

### 2. Enable GitHub Pages

1. Go to repository **Settings**
2. Navigate to **Pages** (left sidebar)
3. Under **Source**, select:
   - **Branch**: `main`
   - **Folder**: `/ (root)`
4. Click **Save**

GitHub Pages will deploy within a few minutes.

### 3. Custom Domain (Optional)

If you want a custom domain like `infin.love`:

**In Repository**:
1. Create/edit `CNAME` file in root
2. Add your domain: `yourdomain.com`
3. Commit and push

**With Domain Registrar**:
1. Add DNS records:
   ```
   Type: A
   Host: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153
   ```
   OR for subdomain (www):
   ```
   Type: CNAME
   Host: www
   Value: YOUR-USERNAME.github.io
   ```
2. Wait for DNS propagation (up to 24 hours)

**Back in GitHub**:
1. Settings → Pages
2. Enter custom domain
3. Save
4. Enable "Enforce HTTPS"

See [GitHub Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) for detailed instructions.

---

## Deployment Process

### Standard Deployment

```bash
# Make changes
git add .
git commit -m "Your commit message"
git push origin main
```

That's it! GitHub Pages deploys automatically.

### Feature Branch Workflow

```bash
# Create feature branch
git checkout -b feature/my-feature

# Make changes and commit
git add .
git commit -m "Add my feature"

# Push branch
git push origin feature/my-feature

# Create Pull Request on GitHub
# After review and approval, merge to main
# Deployment happens automatically
```

### Hotfix Process

For urgent fixes:

```bash
# Create hotfix branch
git checkout -b hotfix/critical-fix

# Fix the issue
git add .
git commit -m "Fix critical issue"

# Push and create PR
git push origin hotfix/critical-fix

# Fast-track review and merge
# Deploy happens automatically
```

---

## Pre-Deployment Checklist

Before deploying to production, verify:

### Local Testing
- [ ] Site works locally (`python -m http.server 8000`)
- [ ] No console errors (F12)
- [ ] All links work
- [ ] Form submission works
- [ ] Mobile menu functions correctly

### Code Quality
- [ ] HTML validates (use [W3C Validator](https://validator.w3.org/))
- [ ] Accessibility checked (Lighthouse, axe DevTools)
- [ ] No spelling errors in content
- [ ] Code follows style guide

### Functional Testing
- [ ] All sections render correctly
- [ ] Navigation works (smooth scroll)
- [ ] Animations perform well
- [ ] Ko-fi widget loads
- [ ] Heart animations don't cause lag

### Cross-Browser Testing
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Mobile Safari (iOS)
- [ ] Chrome Mobile (Android)

### Performance
- [ ] Lighthouse score 90+ (all categories)
- [ ] Page size < 50KB
- [ ] Load time < 2s on 3G

### Security
- [ ] No sensitive data exposed
- [ ] External links have `rel="noopener noreferrer"`
- [ ] CSP header configured
- [ ] HTTPS enabled

See [TESTING.md](TESTING.md) for comprehensive testing procedures.

---

## CI/CD Automation

GitHub Actions automatically run on every push/PR:

### Workflows

1. **HTML Validation** - Checks markup validity
2. **Lighthouse CI** - Performance and accessibility scores
3. **Link Checker** - Finds broken links
4. **Spell Check** - Documentation quality

### Viewing Results

1. Go to **Actions** tab on GitHub
2. Click on workflow run
3. Review results
4. Fix any failures before merging

### Required Checks

For protected branches, require these checks to pass:
- HTML validation
- Lighthouse CI (scores above thresholds)
- No broken links

Configure in: Settings → Branches → Branch protection rules

---

## Rollback Procedures

### If Deployment Breaks Site

**Option 1: Revert Commit**
```bash
# Find problematic commit
git log --oneline

# Revert it
git revert <commit-hash>
git push origin main
```

**Option 2: Force Push Previous Version**
```bash
# CAUTION: Only for emergencies
git reset --hard <last-good-commit>
git push --force origin main
```

**Option 3: Use GitHub UI**
1. Go to commit history
2. Find last good commit
3. Click "Revert" button
4. Create new commit
5. Push to main

### Verify Rollback

- Check https://infin.love loads correctly
- Run smoke tests
- Check GitHub Actions for green checkmarks
- Monitor for user reports

---

## Monitoring Deployment

### Post-Deployment Verification

After deployment completes:

1. **Visit Site**: Ensure https://infin.love loads
2. **Check Key Pages**:
   - Homepage (index.html)
   - 404 page (visit /nonexistent)
   - Mobile view (DevTools or phone)
3. **Test Functions**:
   - Navigation links
   - Form submission
   - Mobile menu
   - External links
4. **Monitor Performance**:
   - Run Lighthouse audit
   - Check PageSpeed Insights
5. **Check Logs**:
   - GitHub Actions results
   - No error badges in README

### Ongoing Monitoring

- **Weekly**: Review GitHub Actions scheduled runs
- **Monthly**: Full Lighthouse audit
- **Quarterly**: Comprehensive security review
- **Yearly**: Dependency updates

---

## Troubleshooting

### Site Not Updating

**Issue**: Changes pushed but site shows old version

**Solutions**:
1. Wait 1-2 minutes (GitHub Pages deploy time)
2. Hard refresh browser (Ctrl+Shift+R or Cmd+Shift+R)
3. Clear browser cache
4. Check GitHub Actions - deployment might have failed
5. Verify branch is set to `main` in Settings → Pages

### 404 Errors

**Issue**: Pages show 404

**Solutions**:
1. Ensure file exists in repository
2. Check CNAME file is correct
3. Verify GitHub Pages is enabled
4. Wait for DNS propagation (custom domains)
5. Check file names (case-sensitive on server)

### SSL Certificate Issues

**Issue**: "Not Secure" or certificate errors

**Solutions**:
1. Settings → Pages → Enforce HTTPS (check)
2. Wait 24 hours for certificate provisioning
3. Verify DNS records point to GitHub
4. Remove and re-add custom domain

### Performance Degradation

**Issue**: Site loads slowly

**Solutions**:
1. Run Lighthouse audit to identify issues
2. Check for large images or files
3. Verify animations are optimized
4. Test on different networks
5. Review recent changes

---

## Alternative Deployment Options

### Netlify

```bash
# netlify.toml
[build]
  publish = "."

[build.processing]
  skip_processing = true
```

Deploy: Connect GitHub repo to Netlify

### Vercel

```bash
# vercel.json
{
  "cleanUrls": true
}
```

Deploy: Connect GitHub repo to Vercel

### Cloudflare Pages

Simply connect GitHub repository - zero configuration needed.

### Why We Use GitHub Pages

- **Free** for open source
- **Zero configuration**
- **Automatic SSL**
- **Global CDN**
- **Great uptime**
- **Integrated with GitHub workflow**

---

## Security Considerations

### Secrets Management

**Current**: No secrets needed (static site)

**If adding backend**:
- Use GitHub Secrets for API keys
- Never commit secrets to repository
- Use environment variables
- Rotate secrets regularly

### Access Control

**Repository Access**:
- Maintainers: Write access
- Contributors: Fork and PR workflow
- Public: Read access

**Deployment Access**:
- Automatic via GitHub Actions
- No manual deployment needed
- Protected main branch (require PR reviews)

---

## Performance Optimization

### Caching Strategy

GitHub Pages automatically:
- Serves files via CDN
- Caches static assets
- Enables gzip compression

### Future: Service Worker

Could add for:
- Offline functionality
- Faster repeat visits
- Background sync

See [ARCHITECTURE.md](ARCHITECTURE.md#future-considerations) for details.

---

## Backup & Recovery

### Backup Strategy

**Git = Backup**:
- Every commit is backed up
- GitHub stores all history
- Can restore any previous version

**Additional Backups**:
```bash
# Clone repository as backup
git clone --mirror https://github.com/Luminous-Dynamics/infin-love.git

# Or download ZIP from GitHub
```

### Disaster Recovery

If GitHub is down:
1. Deploy to alternative host (Netlify, Vercel)
2. Update DNS to point to new host
3. Usually back within hours

If repository deleted:
1. Restore from local clone
2. Create new repository
3. Push all history
4. Reconfigure GitHub Pages

---

## Deployment Checklist

### Before Major Release

- [ ] All tests pass locally
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] Version number bumped (if applicable)
- [ ] Cross-browser tested
- [ ] Accessibility verified
- [ ] Performance benchmarked
- [ ] Security reviewed
- [ ] Backups confirmed
- [ ] Team notified

### Post-Deployment

- [ ] Site loads correctly
- [ ] Key functions work
- [ ] No console errors
- [ ] Mobile works
- [ ] SSL certificate valid
- [ ] Performance acceptable
- [ ] Monitor for issues (24 hours)

---

## Questions?

For deployment questions or issues:

- **Documentation**: [README.md](README.md), [ARCHITECTURE.md](ARCHITECTURE.md)
- **GitHub Pages Docs**: https://docs.github.com/en/pages
- **Issues**: https://github.com/Luminous-Dynamics/infin-love/issues
- **Email**: tristan.stoltz@gmail.com

---

💜 **Deploying love to the world, one push at a time**
