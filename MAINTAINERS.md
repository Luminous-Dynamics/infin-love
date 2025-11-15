# Maintainer Guide 🌟

> *Stewardship as sacred practice. Service as gift. Leadership as love.*

---

## Welcome, Steward!

This guide is for current and future maintainers of Infin.Love. Whether you're Tristan (the founder) revisiting best practices, or a new maintainer joining the circle, this document offers guidance for sacred stewardship.

**Remember:** Maintainership is service, not power. We hold this project for the community, not as owners but as caretakers.

---

## Table of Contents

- [Philosophy of Maintainership](#philosophy-of-maintainership)
- [Daily Responsibilities](#daily-responsibilities)
- [Weekly Tasks](#weekly-tasks)
- [Monthly & Quarterly](#monthly--quarterly)
- [Issue Triage](#issue-triage)
- [Pull Request Review](#pull-request-review)
- [Community Moderation](#community-moderation)
- [Release Process](#release-process)
- [Emergency Procedures](#emergency-procedures)
- [Sustainable Practice](#sustainable-practice)
- [Resources & Tools](#resources--tools)

---

## Philosophy of Maintainership

### Core Principles

**🌟 Service Over Power**
- We serve the community, not rule it
- Authority is responsibility, not privilege
- Power is stewarded, not possessed

**💜 Love as Method**
- Respond with kindness, even when tired
- Assume good intentions
- Prioritize relationship over rules

**🎁 Gift Economy in Practice**
- Maintenance is our gift to the community
- We receive the gift of others' contributions
- The circle sustains us all

**🌱 Sustainable Pace**
- Marathon, not sprint
- Self-care is not selfish
- Burnout serves no one

**🔍 Transparency Always**
- Decisions made in public
- Rationale explained
- Mistakes acknowledged

### Maintainer Mindset

**You are not:**
- The owner or boss
- Required to say yes to everything
- Responsible for everyone's happiness
- Expected to work 24/7
- Perfect or all-knowing

**You are:**
- A steward and facilitator
- Empowered to make thoughtful decisions
- Accountable to shared values
- Worthy of rest and boundaries
- Learning and growing, like everyone

---

## Daily Responsibilities

### Morning Check-In (15-30 minutes)

**Review notifications:**
- [ ] New issues (triage if urgent)
- [ ] New pull requests (acknowledge receipt)
- [ ] Discussion activity (respond if needed)
- [ ] Automated workflow failures
- [ ] Email (Code of Conduct reports, urgent matters)

**Quick triage:**
- Label new issues
- Thank contributors
- Flag anything urgent
- Defer deep work to scheduled time

**Set intention:**
- What needs attention today?
- What can wait?
- How much capacity do I have?

### Throughout the Day (As Capacity Allows)

**Respond to:**
- Questions in discussions (or delegate)
- Comments on open PRs
- Urgent issues (security, broken site)

**Process:**
- Review 1-3 pull requests
- Triage 2-5 issues
- Engage in 1-2 discussions

**Note:** These are guidelines, not quotas. Some days you'll do less, some more.

### End of Day (5-10 minutes)

**Quick review:**
- Anything left in urgent state?
- Any responses promised that need follow-up?
- Tomorrow's priorities clear?

**Self-care check:**
- How's my energy?
- Do I need a break tomorrow?
- Am I feeling resentful? (Sign to adjust boundaries)

---

## Weekly Tasks

### Every Week

**Monday: Set Weekly Intentions**
- [ ] Review open PRs (are any stale?)
- [ ] Check project board/issues
- [ ] Identify priorities for the week
- [ ] Update [PROJECT_STATUS.md](PROJECT_STATUS.md) if needed

**Wednesday: Mid-Week Check**
- [ ] Review progress on weekly goals
- [ ] Respond to accumulated discussions
- [ ] Clear notification backlog

**Friday: Week Wrap-Up**
- [ ] Close completed issues
- [ ] Merge ready PRs
- [ ] Update CHANGELOG if releases pending
- [ ] Celebrate wins! 🎉

### Weekly Community Engagement

**Choose 1-2 per week:**
- Write a community update
- Start a new discussion topic
- Welcome new contributors personally
- Share project milestone
- Highlight a great contribution

### Weekly Metrics Review

**Check (but don't obsess over):**
- GitHub Insights (traffic, activity)
- Open issues count (trending up or down?)
- PR merge velocity
- Community health
- Workflow success rates

---

## Monthly & Quarterly

### Monthly

**Community Health Check:**
- [ ] Review Code of Conduct reports (if any)
- [ ] Check contributor satisfaction
- [ ] Identify areas of friction
- [ ] Celebrate successes
- [ ] Update contributors list

**Documentation Review:**
- [ ] Are docs still accurate?
- [ ] Any common questions to add to FAQ?
- [ ] Links still working? (automated, but double-check)

**Dependency & Security:**
- [ ] Review Dependabot PRs
- [ ] Check for security advisories
- [ ] Update workflows if needed

**Project Planning:**
- [ ] Review roadmap progress
- [ ] Adjust priorities based on community input
- [ ] Update PROJECT_STATUS.md
- [ ] Consider upcoming milestones

### Quarterly

**Major Review:**
- [ ] Governance review (is it working?)
- [ ] Community survey or feedback collection
- [ ] Long-term roadmap adjustment
- [ ] Maintainer self-assessment
- [ ] Consider new maintainer needs

**Transparency Reporting:**
- [ ] Quarterly community update
- [ ] Financial transparency (if applicable)
- [ ] Metrics summary
- [ ] Upcoming plans

### Annually

**Deep Assessment:**
- [ ] Vision alignment check
- [ ] Complete governance review
- [ ] Maintainer continuation decision
- [ ] Major roadmap planning
- [ ] Community retrospective

---

## Issue Triage

### When a New Issue Arrives

**1. Initial Review (2 minutes)**
- Read the issue carefully
- Check if it's actually an issue or a question (→ Discussions)
- Verify it's not a duplicate

**2. Categorize & Label**

Add appropriate labels:
- **Type**: `bug`, `enhancement`, `documentation`, `question`
- **Priority**: `priority: critical`, `priority: high`, `priority: medium`, `priority: low`
- **Area**: `area: accessibility`, `area: design`, `area: documentation`, etc.
- **Effort**: `effort: small`, `effort: medium`, `effort: large`
- **Status**: `status: triage`, `status: confirmed`, `status: blocked`
- **Good First Issue**: If suitable for newcomers

**3. Respond**

Template for acknowledgment:
```markdown
Thank you for reporting this! I've labeled it as [type] and will [action].

[Any questions or clarifications needed]

[Timeline estimate if possible]
```

**4. Decide Next Steps**

- **Critical bug**: Fix immediately or within 24 hours
- **High priority**: Schedule for current week
- **Medium**: Add to backlog, plan for next sprint
- **Low**: Backlog, community may pick up
- **Won't fix**: Explain why and close (with kindness)

### Triage Decision Tree

```
Is site broken/security issue?
  YES → Priority: Critical, fix ASAP
  NO ↓

Is it aligned with values/vision?
  NO → Close with explanation and gratitude
  YES ↓

Is it feasible with current resources?
  NO → Label "help wanted", explain limitations
  YES ↓

Is it a good first issue?
  YES → Label accordingly, add detailed guidance
  NO → Label with effort level

Add to appropriate milestone/project
```

---

## Pull Request Review

### Review Checklist

**1. Automated Checks**
- [ ] All CI/CD workflows passing
- [ ] HTML validation clean
- [ ] Lighthouse scores maintained (95+)
- [ ] No broken links
- [ ] Spelling check passed

**2. Code Quality**
- [ ] Changes align with project values
- [ ] Code follows existing style
- [ ] No security vulnerabilities introduced
- [ ] Accessibility maintained/improved
- [ ] Performance not degraded

**3. Documentation**
- [ ] README updated if needed
- [ ] Comments added for complex logic
- [ ] CHANGELOG.md updated for user-facing changes
- [ ] Related docs updated

**4. Testing**
- [ ] Changes tested locally
- [ ] Edge cases considered
- [ ] Mobile/desktop tested
- [ ] Cross-browser considerations

**5. Community**
- [ ] Contributor welcomed and thanked
- [ ] Feedback given kindly
- [ ] Questions answered
- [ ] Learning opportunity if applicable

### Review Process

**Small PRs (< 50 lines):**
- Quick review (15-30 min)
- Merge if passing all checks
- Thank contributor

**Medium PRs (50-500 lines):**
- Thorough review (30-60 min)
- Request changes if needed (with clear explanations)
- May take 2-3 days for back-and-forth
- Thank and celebrate when merged

**Large PRs (500+ lines):**
- Consider asking to break into smaller PRs
- Extended review time (multiple sessions)
- May need community input
- Extra appreciation for large contribution

### Feedback Template

**Requesting changes:**
```markdown
Thank you for this contribution! I have a few suggestions to make this even better:

**Required changes:**
- [ ] [Specific actionable change with explanation]
- [ ] [Another required change]

**Optional suggestions:**
- Consider [suggestion] because [reasoning]

Let me know if any of this is unclear! Happy to discuss.
```

**Approving:**
```markdown
This looks great! Thank you for:
- [Specific positive thing]
- [Another positive thing]

Merging now! 🎉 Your contribution will be live shortly.
```

### When to Say No

Sometimes we must decline a PR. Do so with kindness:

```markdown
Thank you so much for this contribution! I really appreciate the time and thought you put in.

After careful consideration, I don't think this aligns with [specific reason]:
- [Explanation of why]
- [Alternative approach if applicable]

This doesn't diminish the value of your work! Would you be interested in [alternative contribution]?

Thank you again for your gift to the community. 💜
```

---

## Community Moderation

### Levels of Intervention

**🟢 Level 0: No Action Needed**
- Healthy disagreement
- Constructive feedback
- Self-correcting community

**🟡 Level 1: Gentle Guidance**
- Slightly off-topic
- Unclear communication
- Unintentional minor violation

**Action:** Friendly redirect, clarification, reminder

**🟠 Level 2: Clear Boundary**
- Pattern of behavior concerns
- Moderate Code of Conduct violation
- Escalating conflict

**Action:** Direct message, clear expectation, warning

**🔴 Level 3: Formal Process**
- Serious Code of Conduct violation
- Continued violations after warnings
- Harm to community members

**Action:** Follow [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) enforcement process

### Response Templates

**Off-topic redirect:**
```markdown
This is an interesting point! To keep this thread focused, could you open a new discussion about [topic] in [category]? I'd love to continue this conversation there!
```

**Unkind communication:**
```markdown
I appreciate your passion about this! Let's make sure we're communicating in line with our Code of Conduct. Could you rephrase this focusing on [the idea/code/issue] rather than [the person]?
```

**First warning:**
```markdown
Hi [name], I need to have a conversation about [behavior]. Our Code of Conduct asks that we [expectation], and [specific incident] doesn't align with that.

I assume this wasn't intentional. Can we discuss how to move forward in a way that works for everyone?
```

### When in Doubt

- Consult [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)
- Take time to respond (don't react immediately if upset)
- Seek input from trusted community members
- Prioritize safety over comfort
- Document all moderation actions

---

## Release Process

### When to Release

**Patch (v1.0.X):**
- Bug fixes
- Documentation updates
- Security patches
- Every 2-4 weeks or as needed

**Minor (v1.X.0):**
- New features
- Significant improvements
- Major documentation additions
- Every 2-3 months

**Major (vX.0.0):**
- Breaking changes
- Major redesigns
- Significant scope changes
- Rare, planned carefully

### Release Checklist

**Preparation:**
- [ ] All planned PRs merged
- [ ] All tests passing
- [ ] Documentation updated
- [ ] CHANGELOG.md updated with all changes
- [ ] Version number decided

**Release:**
- [ ] Update version in relevant files
- [ ] Create git tag: `git tag v1.x.x`
- [ ] Push tag: `git push origin v1.x.x`
- [ ] GitHub release workflow runs automatically
- [ ] Verify release created on GitHub

**Communication:**
- [ ] Announcement in Discussions
- [ ] Thank all contributors
- [ ] Highlight major changes
- [ ] Link to CHANGELOG

**Template:**
```markdown
## Infin.Love v1.x.x Released! 🎉

We're excited to announce v1.x.x with [brief description]!

### ✨ Highlights
- [Major change 1]
- [Major change 2]

### 🙏 Gratitude
Thank you to everyone who contributed to this release:
@contributor1, @contributor2, @contributor3

### 📋 Full Changelog
See [CHANGELOG.md](CHANGELOG.md) for complete details.

### 🚀 What's Next
[Brief preview of upcoming work]

Thank you for being part of this gift circle! 💜
```

---

## Emergency Procedures

### Site Down or Broken

**Immediate actions:**
1. Verify the issue
2. Check GitHub Pages status
3. Review recent commits
4. Post incident notice in Discussions
5. Revert if necessary
6. Fix and deploy
7. Post resolution update

**Template:**
```markdown
## Incident Notice

We're aware of [issue]. Working on a fix now.

**Status:** [Investigating/Fixing/Resolved]
**Impact:** [Who's affected]
**ETA:** [If known]

Updates posted here.
```

### Security Vulnerability

**Immediate actions:**
1. Do NOT discuss publicly yet
2. Assess severity (use CVSS if helpful)
3. Develop fix
4. Test thoroughly
5. Deploy quietly if critical
6. Public disclosure after fix deployed
7. Update [SECURITY.md](SECURITY.md)

**See:** [SECURITY.md](SECURITY.md) for full policy

### Code of Conduct Crisis

**Immediate actions:**
1. Ensure victim safety
2. Follow [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) process
3. Document everything
4. Consult trusted advisors if needed
5. Communicate clearly with all parties
6. Implement consequences if necessary
7. Support healing and learning

**Priority:** Safety > Comfort > Code

---

## Sustainable Practice

### Preventing Burnout

**Warning signs:**
- Dreading notifications
- Resentment toward contributors
- Procrastinating on maintenance
- Feeling obligated rather than inspired
- Neglecting self-care

**Immediate responses:**
- Take a break (announce it!)
- Reduce scope
- Ask for help
- Set clearer boundaries
- Reassess commitments

### Healthy Boundaries

**It's okay to:**
- Not respond immediately
- Take days off
- Say "not now"
- Say "no" to features
- Ask others for help
- Step down if needed

**Set expectations:**
- Response time: "Within 3 days" not "immediately"
- Availability: "M-F during work hours" not "24/7"
- Scope: "These features" not "anything anyone wants"

### Self-Care Practices

**Daily:**
- Take breaks between tasks
- Move your body
- Stay hydrated
- Stop at a reasonable time

**Weekly:**
- At least one full day off
- Engage in non-Infin.Love activities
- Connect with loved ones
- Do something just for fun

**Monthly:**
- Review boundaries
- Celebrate wins
- Adjust workload if needed
- Gratitude practice

**Remember:** You can't pour from an empty cup. Your wellbeing enables the project's wellbeing.

---

## Resources & Tools

### Essential Reading

**Internal docs:**
- [GOVERNANCE.md](GOVERNANCE.md) - How we decide
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) - Community standards
- [VISION.md](VISION.md) - Where we're headed
- [CONTRIBUTING.md](CONTRIBUTING.md) - How others contribute
- [ROADMAP.md](ROADMAP.md) - What's planned

**External resources:**
- [GitHub Docs](https://docs.github.com/) - GitHub features
- [Maintainer Guide](https://opensource.guide/best-practices/) - Open source best practices
- [Contributor Covenant](https://www.contributor-covenant.org/) - Community standards

### Tools & Automation

**GitHub Features:**
- Actions (CI/CD) - Automated testing
- Discussions - Community conversations
- Projects - Task management
- Insights - Metrics and analytics

**Workflows:**
- HTML validation - Quality assurance
- Lighthouse CI - Performance monitoring
- Link checker - Documentation health
- Spell check - Writing quality
- Auto-labeler - Organization
- Welcome bot - New contributor experience

**Local Tools:**
- Browser DevTools - Testing
- Screen reader - Accessibility testing
- Git - Version control
- Text editor - Code editing

### Communication Templates

**Stored in:**
- `.github/ISSUE_TEMPLATE/` - Issue templates
- `.github/DISCUSSION_TEMPLATE/` - Discussion templates
- `.github/pull_request_template.md` - PR template
- This document - Response templates

### Getting Help

**When you need support:**
- Community: Post in Discussions
- Other maintainers: Email or private channel (when we have multiple maintainers)
- Advisors: Reach out to trusted open source maintainers
- Therapy: Seriously, maintainership can be emotionally taxing

**You don't have to do this alone!**

---

## Succession Planning

### When You Need to Step Down

**It's okay to:**
- Step down temporarily (burnout recovery)
- Step down permanently (life changes)
- Reduce involvement (shift to advisory role)

**Process:**
1. Reflect on decision
2. Announce intention (2+ weeks notice if possible)
3. Document current state
4. Identify potential successors
5. Support transition
6. Hand off access and credentials
7. Say goodbye with grace

**Template:**
```markdown
After [time period] of maintaining Infin.Love, I've decided to [step down/reduce involvement/transition to advisory].

This wasn't an easy decision. I love this community and project. [Brief reason without oversharing]

[For permanent step-down:]
I'm committed to finding a successor who shares our values and will serve this community well.

[For temporary:]
I expect to return [timeframe] and will stay in touch.

Thank you for everything. This has been one of the most meaningful experiences of my life.

With love and gratitude,
[Name]
```

### Finding New Maintainers

**Look for:**
- Sustained contribution (1+ years)
- Values alignment
- Community trust
- Communication skills
- Emotional maturity
- Technical competence (but this is learnable!)

**Process:**
1. Identify candidates
2. Private invitation to discuss
3. Trial period (3-6 months) with increasing responsibility
4. Full access if successful
5. Public announcement and celebration

---

## Closing Thoughts

### Remember Why

On hard days, remember:
- You're building something beautiful
- You're serving a community of souls
- You're modeling sacred reciprocity
- Your work matters
- You are loved and appreciated

### You Are Enough

You don't have to be perfect. You don't have to do everything. You don't have to make everyone happy.

Just do your best, with love, sustainable, and aligned with values.

**That is enough. You are enough.**

### Gratitude

Thank you for your stewardship. Thank you for your service. Thank you for your love.

This project exists because you care for it. The community thrives because you tend to it.

**You are a gift.** 💜

---

<div align="center">

**"The gift must always move."** 💜

*Maintained with love • Held with care • Shared with gratitude*

**For support:** tristan.stoltz@gmail.com

**[⬆ Back to Top](#maintainer-guide-)**

</div>
