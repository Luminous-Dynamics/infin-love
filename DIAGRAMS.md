# Visual Diagrams 📊

> *Understanding Infin.Love through visual representations*

This document provides visual diagrams to help you understand complex workflows, architecture, and processes. All diagrams use [Mermaid](https://mermaid.js.org/) which renders automatically on GitHub.

---

## Contribution Workflow

```mermaid
graph TD
    A[Fork Repository] --> B[Clone to Local]
    B --> C[Create Feature Branch]
    C --> D[Make Changes]
    D --> E[Test Locally]
    E --> F{Tests Pass?}
    F -->|No| D
    F -->|Yes| G[Commit Changes]
    G --> H[Push to Fork]
    H --> I[Create Pull Request]
    I --> J[Automated CI Checks]
    J --> K{All Checks Pass?}
    K -->|No| L[Fix Issues]
    L --> D
    K -->|Yes| M[Maintainer Review]
    M --> N{Approved?}
    N -->|Changes Requested| O[Address Feedback]
    O --> D
    N -->|Yes| P[Merge to Main]
    P --> Q[Auto-Deploy to Production]
    Q --> R[Celebrate! 🎉]
```

**Learn more:** [CONTRIBUTING.md](CONTRIBUTING.md)

---

## Learning Path Journey

```mermaid
graph LR
    A[Choose Your Path] --> B[Complete Beginner]
    A --> C[Web Dev Beginner]
    A --> D[Experienced Developer]
    A --> E[Accessibility Specialist]
    A --> F[Documentation Writer]
    A --> G[Designer/UX]
    A --> H[Community Builder]

    B --> I[First Contribution]
    C --> I
    D --> J[High-Impact Work]
    E --> K[A11y Improvements]
    F --> L[Doc Enhancements]
    G --> M[Design Contributions]
    H --> N[Community Programs]

    I --> O[Regular Contributor]
    J --> O
    K --> O
    L --> O
    M --> O
    N --> O

    O --> P[Core Contributor]
    P --> Q[Maintainer]
```

**Learn more:** [LEARNING_PATHS.md](LEARNING_PATHS.md)

---

## CI/CD Pipeline

```mermaid
graph TD
    A[Git Push] --> B{On Main Branch?}
    B -->|Yes| C[All Workflows]
    B -->|No| D[PR Workflows Only]

    C --> E[HTML Validation]
    C --> F[Lighthouse CI]
    C --> G[CodeQL Security]
    C --> H[Link Checker]
    C --> I[Spell Check]
    C --> J[Dependency Review]

    D --> E
    D --> F
    D --> H
    D --> I
    D --> J

    E --> K{All Pass?}
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K

    K -->|No| L[CI Fails - Fix Required]
    K -->|Yes on Main| M[Auto-Deploy to GitHub Pages]
    K -->|Yes on PR| N[Ready for Review]

    M --> O[Live at infin.love]
```

**Learn more:** [TESTING.md](TESTING.md)

---

## Project Architecture

```mermaid
graph TD
    A[infin.love] --> B[GitHub Pages Hosting]
    B --> C[index.html]
    B --> D[404.html]
    B --> E[manifest.json]

    C --> F[HTML Structure]
    C --> G[Embedded CSS]
    C --> H[Embedded JavaScript]

    F --> I[Semantic HTML5]
    F --> J[ARIA Labels]
    F --> K[Accessibility Features]

    G --> L[Design System Variables]
    G --> M[Responsive Layouts]
    G --> N[Animations]

    H --> O[Smooth Scrolling]
    H --> P[Form Handling]
    H --> Q[Heart Animations]

    E --> R[PWA Capabilities]
    R --> S[Installable]
    R --> T[Offline-Ready]

    B --> U[External Services]
    U --> V[Formspree - Forms]
    U --> W[Ko-fi - Donations]
```

**Learn more:** [ARCHITECTURE.md](ARCHITECTURE.md)

---

## Documentation Structure

```mermaid
graph TD
    A[Documentation Hub] --> B[Getting Started]
    A --> C[Development]
    A --> D[Community]
    A --> E[Governance]

    B --> B1[QUICK_START.md]
    B --> B2[LEARNING_PATHS.md]
    B --> B3[ONBOARDING.md]
    B --> B4[EXAMPLES.md]
    B --> B5[TROUBLESHOOTING.md]

    C --> C1[CONTRIBUTING.md]
    C --> C2[DESIGN.md]
    C --> C3[ARCHITECTURE.md]
    C --> C4[TESTING.md]
    C --> C5[DEPLOYMENT.md]

    D --> D1[COMMUNITY.md]
    D --> D2[VISION.md]
    D --> D3[ROADMAP.md]
    D --> D4[CODE_OF_CONDUCT.md]
    D --> D5[PRESS_KIT.md]

    E --> E1[GOVERNANCE.md]
    E --> E2[MAINTAINERS.md]
    E --> E3[SECURITY.md]
    E --> E4[ANALYTICS.md]
```

**Learn more:** [README.md](README.md#-documentation)

---

## Security Scanning Flow

```mermaid
graph TD
    A[Code Changes] --> B[Push/PR Created]
    B --> C[CodeQL Scan]
    B --> D[Dependency Review]

    C --> E[JavaScript Analysis]
    C --> F[Security Patterns]
    C --> G[Quality Checks]

    D --> H[Vulnerability Scan]
    D --> I[License Check]
    D --> J[Outdated Dependencies]

    E --> K{Issues Found?}
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K

    K -->|Yes - Critical| L[Block Merge]
    K -->|Yes - High| M[Warning]
    K -->|No| N[Approve]

    L --> O[Fix Required]
    M --> P[Review & Decide]
    N --> Q[Safe to Merge]
```

**Learn more:** [SECURITY.md](SECURITY.md)

---

## Gift Circle Flow

```mermaid
graph LR
    A[Individual] -->|Gives Freely| B[Gift Circle]
    B -->|Receives| A
    B -->|Flows to| C[Community]
    C -->|Returns Transformed| B
    B -->|Trust & Abundance| D[Sustainable Community]

    style B fill:#E91E63,color:#fff
    style D fill:#9C27B0,color:#fff
```

**vs. Traditional Exchange:**

```mermaid
graph LR
    A[Person A] -->|Give X| B[Transaction]
    B -->|Receive Y| A
    A -->|Expectation| B
    B -->|Obligation| A

    style B fill:#666,color:#fff
```

**Learn more:** [COMMUNITY.md](COMMUNITY.md)

---

## Issue Lifecycle

```mermaid
stateDiagram-v2
    [*] --> Opened: Issue Created
    Opened --> Triaged: Maintainer Reviews
    Triaged --> Labeled: Labels Added
    Labeled --> Assigned: Contributor Claims
    Assigned --> InProgress: Work Begins
    InProgress --> PRCreated: Pull Request
    PRCreated --> UnderReview: Review Requested
    UnderReview --> ChangesRequested: Feedback Given
    ChangesRequested --> InProgress: Updates Made
    UnderReview --> Approved: Looks Good!
    Approved --> Merged: PR Merged
    Merged --> Closed: Issue Resolved

    Labeled --> Stale: 60 Days Inactive
    Stale --> Closed: 14 Days Warning
    Stale --> InProgress: Activity Resumed

    Closed --> [*]
```

**Learn more:** [CONTRIBUTING.md](CONTRIBUTING.md)

---

## Accessibility Testing Process

```mermaid
graph TD
    A[Code Changes] --> B[Automated Tests]
    A --> C[Manual Tests]

    B --> D[Lighthouse Audit]
    B --> E[axe DevTools]
    B --> F[WAVE]

    C --> G[Keyboard Navigation]
    C --> H[Screen Reader]
    C --> I[Color Contrast]
    C --> J[Zoom to 200%]

    D --> K{WCAG 2.1 AA?}
    E --> K
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K

    K -->|Pass| L[Accessibility Approved]
    K -->|Fail| M[Fix Issues]
    M --> A

    L --> N[Deploy]
```

**Learn more:** [TESTING.md](TESTING.md#accessibility-testing)

---

## Release Process

```mermaid
graph TD
    A[Ready to Release] --> B[Update CHANGELOG.md]
    B --> C[Bump Version Numbers]
    C --> D[Create Git Tag]
    D --> E[Push to Main]
    E --> F[Automated Tests Run]
    F --> G{All Tests Pass?}
    G -->|No| H[Fix Issues]
    H --> E
    G -->|Yes| I[Create GitHub Release]
    I --> J[Auto-Deploy to Production]
    J --> K[Announce to Community]
    K --> L[Update PROJECT_STATUS.md]
    L --> M[Release Complete! 🎉]
```

**Learn more:** [DEPLOYMENT.md](DEPLOYMENT.md)

---

## Contributor Recognition Flow

```mermaid
graph TD
    A[Contribution Made] --> B{Type?}

    B -->|Code| C[Automated: PR Merged]
    B -->|Docs| C
    B -->|Design| C
    B -->|Other| D[Manual: Maintainer Adds]

    C --> E[All-Contributors Bot]
    D --> E

    E --> F[Update CONTRIBUTORS.md]
    F --> G[Add to README Badge]
    G --> H[Thank in Release Notes]
    H --> I[Community Recognition]

    I --> J[Contributor Celebrated! 🎉]
```

**Learn more:** [CONTRIBUTORS.md](CONTRIBUTORS.md)

---

## Deployment Workflow

```mermaid
graph TD
    A[Local Development] --> B[Test Changes Locally]
    B --> C{Tests Pass?}
    C -->|No| A
    C -->|Yes| D[Commit to Feature Branch]
    D --> E[Push to Fork]
    E --> F[Create Pull Request]
    F --> G[CI/CD Checks Run]
    G --> H{All Checks Pass?}
    H -->|No| I[Review Failures]
    I --> A
    H -->|Yes| J[Code Review]
    J --> K{Approved?}
    K -->|Changes Requested| A
    K -->|Yes| L[Merge to Main]
    L --> M[GitHub Pages Detects Push]
    M --> N[Validation Workflows Run]
    N --> O{Workflows Pass?}
    O -->|No| P[Rollback/Fix]
    P --> A
    O -->|Yes| Q[GitHub Pages Builds Site]
    Q --> R[Deploy to CDN]
    R --> S[Live at infin.love]
    S --> T[Deployed! 🚀]
```

**Learn more:** [DEPLOYMENT.md](DEPLOYMENT.md)

---

## Testing Workflow

```mermaid
graph TD
    A[Start Testing] --> B[HTML Validation]
    B --> C[Keyboard Navigation Test]
    C --> D{Can Navigate Entire Site?}
    D -->|No| E[Fix Focus Issues]
    E --> C
    D -->|Yes| F[Screen Reader Test]
    F --> G{Announces Correctly?}
    G -->|No| H[Fix ARIA/Semantics]
    H --> F
    G -->|Yes| I[Cross-Browser Test]
    I --> J{Works in All Browsers?}
    J -->|No| K[Fix Compatibility]
    K --> I
    J -->|Yes| L[Mobile Responsive Test]
    L --> M{Works on Mobile?}
    M -->|No| N[Fix Responsive CSS]
    N --> L
    M -->|Yes| O[Performance Test]
    O --> P{Lighthouse 95+?}
    P -->|No| Q[Optimize Performance]
    Q --> O
    P -->|Yes| R[Accessibility Audit]
    R --> S{WCAG AA Compliant?}
    S -->|No| T[Fix A11y Issues]
    T --> R
    S -->|Yes| U[All Tests Pass! ✅]
```

**Learn more:** [TESTING.md](TESTING.md)

---

## Documentation Contribution Flow

```mermaid
graph TD
    A[Identify Doc Need] --> B{Doc Exists?}
    B -->|No| C[Create New Doc]
    B -->|Yes| D[Enhance Existing Doc]

    C --> E[Follow Markdown Style]
    D --> E

    E --> F[Add Cross-References]
    F --> G[Update INDEX.md]
    G --> H[Add to PROJECT_STATUS]
    H --> I[Update CHANGELOG]
    I --> J[Add Terms to .wordlist.txt]
    J --> K[Test All Links]
    K --> L{Links Work?}
    L -->|No| M[Fix Broken Links]
    M --> K
    L -->|Yes| N[Run Spell Check]
    N --> O{Passes?}
    O -->|No| P[Fix Typos/Add Words]
    P --> N
    O -->|Yes| Q[Submit PR]
    Q --> R[Automated Checks]
    R --> S{Checks Pass?}
    S -->|No| T[Review Failures]
    T --> E
    S -->|Yes| U[Maintainer Review]
    U --> V{Approved?}
    V -->|Changes Requested| E
    V -->|Yes| W[Merge & Deploy]
    W --> X[Doc Live! 📚]
```

**Learn more:** [CONTRIBUTING.md](CONTRIBUTING.md) • [INDEX.md](INDEX.md)

---

## Metrics Tracking Workflow

```mermaid
graph TD
    A[First Monday of Month] --> B[Review GitHub Insights]
    B --> C[Check Traffic Stats]
    B --> D[Review Issues/PRs]
    B --> E[Check Contributors]

    C --> F[Automated Metrics]
    D --> F
    E --> F

    F --> G[Lighthouse CI Results]
    F --> H[CodeQL Status]
    F --> I[Link Checker Status]
    F --> J[Spell Check Status]

    G --> K[Update METRICS.md]
    H --> K
    I --> K
    J --> K

    K --> L[Qualitative Assessment]
    L --> M[Community Sentiment]
    L --> N[Maintainer Wellbeing]
    L --> O[Values Alignment]

    M --> P[Document Insights]
    N --> P
    O --> P

    P --> Q{Quarter End?}
    Q -->|No| R[Monthly Complete]
    Q -->|Yes| S[Quarterly Deep Analysis]
    S --> T[Trend Review]
    T --> U[Goal Assessment]
    U --> V[Strategic Planning]
    V --> W[Update ROADMAP]
    W --> R

    R --> X{Year End?}
    X -->|No| Y[Done! 📊]
    X -->|Yes| Z[Annual Reflection]
    Z --> AA[Comprehensive Review]
    AA --> AB[Impact Assessment]
    AB --> AC[Vision Alignment]
    AC --> Y
```

**Learn more:** [METRICS.md](METRICS.md) • [PROJECT_STATUS.md](PROJECT_STATUS.md)

---

## Using These Diagrams

### View on GitHub
All diagrams render automatically when viewing this file on GitHub.

### Edit Diagrams
1. Use [Mermaid Live Editor](https://mermaid.live/)
2. Copy diagram code
3. Make changes
4. Test rendering
5. Submit PR with updates

### Add New Diagrams
We welcome new diagrams! Consider adding:
- User journeys
- Data flow diagrams
- Sequence diagrams
- State machines

See [Mermaid Documentation](https://mermaid.js.org/intro/) for syntax.

---

<div align="center">

**Visual thinking aids understanding** 💡

**Suggest improvements:** [Open an Issue](https://github.com/Luminous-Dynamics/infin-love/issues/new?template=feature_request.yml)

[⬆ Back to Top](#visual-diagrams-)

</div>
