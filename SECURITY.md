# Security Policy 🔒

**See also:** [CONTRIBUTING.md](CONTRIBUTING.md) - Secure development practices • [TESTING.md](TESTING.md) - Security testing • [DEPLOYMENT.md](DEPLOYMENT.md) - Secure deployment

## Our Commitment to Security

The safety and privacy of visitors to Infin.Love is sacred to us. We take security vulnerabilities seriously and appreciate the efforts of security researchers and community members who help keep this space safe.

## Supported Versions

Since this is a static website hosted on GitHub Pages, we maintain only the latest published version:

| Version | Supported          |
| ------- | ------------------ |
| Latest (main branch) | ✅ Actively maintained |
| Older commits | ❌ Not supported |

## Security Features Currently Implemented

Our site includes several security measures:

- **Content Security Policy (CSP)**: Restricts resource loading to trusted sources
- **HTTPS Only**: All traffic encrypted via GitHub Pages
- **No Server-Side Processing**: Static site reduces attack surface
- **External Link Protection**: `rel="noopener noreferrer"` on external links
- **Form Security**: Formspree handles form submissions securely
- **Minimal Dependencies**: Only Ko-fi widget as external script
- **No User Data Storage**: No cookies, localStorage, or tracking

## Reporting a Vulnerability

If you discover a security vulnerability, please help us address it responsibly.

### **What to Report**

Please report:
- Cross-site scripting (XSS) vulnerabilities
- Content Security Policy bypasses
- Authentication or authorization flaws (if any)
- Information disclosure issues
- Dependency vulnerabilities
- Social engineering vectors
- Any issue that could compromise user privacy or safety

### **How to Report**

**Email**: tristan.stoltz@gmail.com

**Subject line**: `[SECURITY] Brief description`

**Please include**:
1. **Description**: Clear explanation of the vulnerability
2. **Impact**: What could an attacker do? Who is affected?
3. **Steps to Reproduce**: Detailed steps to verify the issue
4. **Proof of Concept**: Code, screenshots, or demo (if applicable)
5. **Suggested Fix**: Your thoughts on remediation (optional)
6. **Disclosure Timeline**: When you plan to publicly disclose (if at all)

**Please do NOT**:
- Publicly disclose the vulnerability before we've had time to address it
- Access, modify, or delete user data (this site doesn't store any, but in general)
- Perform destructive testing (DoS attacks, etc.)
- Social engineer, phish, or physically attack our infrastructure

### **What to Expect**

1. **Acknowledgment**: Within 48 hours of your report
2. **Assessment**: We'll evaluate the issue and determine severity
3. **Updates**: Regular communication about our progress
4. **Resolution**: A fix deployed as quickly as possible
5. **Credit**: Recognition for your responsible disclosure (if desired)

**Typical Timeline**:
- **Critical vulnerabilities**: Fixed within 24-48 hours
- **High severity**: Fixed within 1 week
- **Medium severity**: Fixed within 2 weeks
- **Low severity**: Fixed in next scheduled update

## Security Best Practices for Contributors

If you're contributing code, please:

### **Input Handling**
- Never use `innerHTML` with user-provided content
- Use `textContent` or `innerText` for dynamic content
- Sanitize any user input (though we minimize this)

### **External Resources**
- Only load scripts from trusted CDNs
- Use Subresource Integrity (SRI) hashes when possible
- Minimize third-party dependencies

### **Content Security Policy**
- Test changes against our CSP
- Update CSP if new sources are needed
- Document any CSP modifications in PR

### **Forms and Data**
- Never send sensitive data in URLs
- Use HTTPS for all form submissions
- Implement CSRF protection if adding backend features

### **Dependencies**
- Keep external libraries updated
- Review dependency security advisories
- Prefer no dependencies when possible

## Known Limitations & Accepted Risks

We acknowledge these limitations:

### **Third-Party Services**
- **Ko-fi Widget**: External script loaded from storage.ko-fi.com
  - Risk: Potential XSS if Ko-fi is compromised
  - Mitigation: CSP restricts to HTTPS, async loading
  - Status: Accepted risk for donation functionality

- **Formspree**: Form submissions sent to external service
  - Risk: User emails processed by third party
  - Mitigation: Privacy policy disclosed, HTTPS only
  - Status: Accepted risk for email collection

### **Static Site Limitations**
- No rate limiting on form submissions (handled by Formspree)
- No backend validation (client-side only)
- Relies on GitHub Pages infrastructure

## Security Updates

When we fix security vulnerabilities:

1. **Patch**: Deploy fix immediately
2. **Notify**: Email reporters and update this file
3. **Document**: Add to CHANGELOG (coming soon)
4. **Learn**: Update practices to prevent similar issues

## Questions or Concerns?

If you have questions about our security practices:
- Open an issue (for non-sensitive questions)
- Email: tristan.stoltz@gmail.com (for sensitive topics)

## Responsible Disclosure Recognition

We deeply appreciate security researchers who:
- Report vulnerabilities responsibly
- Give us time to fix issues before disclosure
- Help make the internet safer for everyone

With your permission, we'll recognize you in:
- This SECURITY.md file
- Release notes
- Our contributors list

Thank you for helping keep Infin.Love safe and sacred. 🙏

---

**Last Updated**: January 2025

**Contact**: tristan.stoltz@gmail.com
