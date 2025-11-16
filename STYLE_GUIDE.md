# Documentation Style Guide 📝

> *Consistency creates clarity. Clarity serves love.*

This guide ensures all Infin.Love documentation maintains consistent style, tone, and formatting. Follow these guidelines when creating or updating documentation.

**See also:** [CONTRIBUTING.md](CONTRIBUTING.md) • [EXAMPLES.md](EXAMPLES.md) • [GLOSSARY.md](GLOSSARY.md)

---

## Table of Contents

- [Philosophy](#philosophy)
- [Markdown Formatting](#markdown-formatting)
- [Document Structure](#document-structure)
- [Writing Style](#writing-style)
- [Terminology](#terminology)
- [Cross-References](#cross-references)
- [Code Examples](#code-examples)
- [Lists and Tables](#lists-and-tables)
- [Emojis](#emojis)
- [File Naming](#file-naming)

---

## Philosophy

### Core Principles

**Accessibility First**
- Write for screen readers
- Use semantic markdown
- Provide alt text for images
- Use descriptive link text

**Clarity Over Cleverness**
- Simple, direct language
- Short paragraphs (3-5 sentences)
- Active voice preferred
- Concrete examples over abstract concepts

**Inclusive Language**
- Welcome all skill levels
- Assume good intent
- Avoid jargon (or explain it)
- Use "we" and "you" (not "they" or "one")

**Sacred Tone**
- Warm and welcoming
- Respectful and kind
- Encouraging, not intimidating
- Mindful of gift economy values

---

## Markdown Formatting

### Headers

**H1 - Document Title** (One per document)
```markdown
# Document Title 🎨
```

**H2 - Major Sections**
```markdown
## Section Name
```

**H3 - Subsections**
```markdown
### Subsection Name
```

**H4 and Below** - Use sparingly
```markdown
#### Minor Heading
```

**Guidelines:**
- ✅ Use sentence case ("Getting started" not "Getting Started")
- ✅ Add emoji to H1 only (optional but encouraged)
- ✅ Use descriptive, scannable headers
- ❌ Don't skip heading levels (H1 → H3)
- ❌ Don't use punctuation at end of headers

### Emphasis

**Bold** - For emphasis and UI elements
```markdown
**important term** or **Button Name**
```

**Italic** - For terminology introduction
```markdown
*sacred reciprocity* is the practice of...
```

**Code** - For inline code, file names, commands
```markdown
Use the `git commit` command
Edit `README.md`
```

**Guidelines:**
- ✅ Use bold sparingly for true emphasis
- ✅ Use italics for first mention of key terms
- ✅ Use code formatting for all technical references
- ❌ Don't use ALL CAPS for emphasis

### Links

**Internal Links** - To other docs
```markdown
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines
```

**External Links** - To websites
```markdown
Learn more at [Mermaid Documentation](https://mermaid.js.org/)
```

**Anchor Links** - To sections within doc
```markdown
Jump to [Installation](#installation)
```

**Guidelines:**
- ✅ Use descriptive link text ("read the guide" not "click here")
- ✅ Include file extension for internal links
- ✅ Verify all links work before committing
- ❌ Don't use bare URLs in prose (embed them)

---

## Document Structure

### Standard Document Template

```markdown
# Document Title 🎨

> *One-sentence description or quote*

**See also:** [Related Doc 1](doc1.md) • [Related Doc 2](doc2.md)

---

## Introduction

Brief overview of what this document covers.

---

## Main Content Sections

### Subsection 1

Content here...

### Subsection 2

Content here...

---

## Related Resources

- Link to related documentation
- External resources if applicable

---

<div align="center">

**Encouraging closing message** 💜

**Questions?** See [SUPPORT.md](SUPPORT.md)

Built with consciousness • Shared with love • Held in sacred reciprocity

[⬆ Back to Top](#document-title-)

</div>
```

### Required Elements

**All Documentation Must Have:**
1. **H1 Title** with optional emoji
2. **Brief description** (quote or one-liner in blockquote)
3. **Cross-references** to related docs (if applicable)
4. **Clear sections** with H2 headers
5. **Closing section** with resources/next steps
6. **Back to top link** at bottom

**Longer Docs (>200 lines) Should Have:**
- Table of contents (after intro)
- Section dividers (`---`)
- Clear navigation aids

---

## Writing Style

### Tone

**Do:**
- ✅ Be warm and welcoming
- ✅ Encourage and support
- ✅ Acknowledge difficulty ("This can be tricky...")
- ✅ Celebrate progress ("Great job!")
- ✅ Use "we" and "you" for inclusivity

**Don't:**
- ❌ Be condescending or patronizing
- ❌ Assume prior knowledge without providing resources
- ❌ Use aggressive language ("you must", "never do")
- ❌ Create anxiety or pressure
- ❌ Use sarcasm or irony

### Voice

**Active Voice Preferred:**
```markdown
✅ "Run the tests before committing"
❌ "Tests should be run before commits are made"
```

**Present Tense Preferred:**
```markdown
✅ "The script validates HTML"
❌ "The script will validate HTML"
```

**Direct Instructions:**
```markdown
✅ "1. Clone the repository"
❌ "The first step involves cloning the repository"
```

### Sentence Structure

**Short and Clear:**
```markdown
✅ "This guide helps you contribute. Follow the steps below."
❌ "This comprehensive guide is designed to help you understand the contribution process by providing step-by-step instructions that will enable you to successfully contribute to the project."
```

**One Idea Per Sentence:**
```markdown
✅ "Fork the repository. Then clone it locally."
❌ "Fork the repository and then clone it locally to your machine so you can make changes."
```

---

## Terminology

### Consistent Terms

Use these standardized terms:

**Project Terms:**
- "Infin.Love" (capital I, L - not "infin.love" in prose)
- "sacred reciprocity" (lowercase unless starting sentence)
- "gift economy" (lowercase)
- "gift circle" (not "gift-circle")
- "contributor" (not "developer" unless specifically coding)
- "maintainer" (not "owner" or "admin")

**Technical Terms:**
- "repository" (not "repo" in documentation)
- "pull request" or "PR" (both acceptable)
- "commit message" (not "commit comment")
- "workflow" (not "pipeline" unless specifically GitHub Actions)
- "documentation" (not "docs" in headers, acceptable in prose)

**Sacred Terms:**
- See [GLOSSARY.md](GLOSSARY.md) for full definitions
- Always use consistent terminology
- Define terms on first use in each doc
- Link to GLOSSARY for detailed definitions

### Terminology Dos and Don'ts

**Do:**
- ✅ Define specialized terms on first use
- ✅ Link to GLOSSARY for comprehensive definitions
- ✅ Use consistent capitalization
- ✅ Spell out acronyms first time: "Continuous Integration (CI)"

**Don't:**
- ❌ Use slang or colloquialisms
- ❌ Vary terminology for same concept
- ❌ Assume readers know technical jargon
- ❌ Use abbreviations without defining them

---

## Cross-References

### When to Cross-Reference

**Always cross-reference when:**
- Mentioning related documentation
- Pointing to examples or patterns
- Directing to troubleshooting resources
- Referencing external learning materials

### Cross-Reference Format

**At Document Top:**
```markdown
**See also:** [DOC1.md](DOC1.md) - Brief description • [DOC2.md](DOC2.md) - Brief description
```

**In Content:**
```markdown
For more details, see [CONTRIBUTING.md](CONTRIBUTING.md).

Learn more in our [contribution guide](CONTRIBUTING.md).

**Next step:** Follow [QUICK_START.md](QUICK_START.md)
```

**At Document Bottom:**
```markdown
## Related Documentation

- [DOC1](DOC1.md) - When to use this
- [DOC2](DOC2.md) - Related topic
- [External Resource](https://example.com) - Supplementary learning
```

### Cross-Reference Best Practices

**Do:**
- ✅ Provide context for why reader should follow link
- ✅ Use descriptive link text
- ✅ Group related links together
- ✅ Verify links work

**Don't:**
- ❌ Overload with too many links (max 3-4 in "See also")
- ❌ Create circular references
- ❌ Link to external sites without context
- ❌ Use "click here" as link text

---

## Code Examples

### Code Blocks

**With Language Specification:**
```markdown
\`\`\`javascript
function hello() {
    console.log("Hello, World!");
}
\`\`\`
```

**With Comments:**
```markdown
\`\`\`bash
# Clone the repository
git clone https://github.com/user/repo.git

# Navigate to directory
cd repo
\`\`\`
```

**Command Output:**
```markdown
\`\`\`
$ git status
On branch main
Your branch is up to date
\`\`\`
```

### Good vs. Bad Examples

**Show Both When Helpful:**
```markdown
✅ **Good:**
\`\`\`html
<button aria-label="Close menu">X</button>
\`\`\`

❌ **Bad:**
\`\`\`html
<button>X</button>
\`\`\`
```

### Code Example Guidelines

**Do:**
- ✅ Include language specification in code fence
- ✅ Add comments explaining complex parts
- ✅ Show realistic, working examples
- ✅ Format code consistently (4-space indent)

**Don't:**
- ❌ Show broken or pseudo-code (unless explicitly noted)
- ❌ Use overly complex examples
- ❌ Forget syntax highlighting
- ❌ Skip error handling in production examples

---

## Lists and Tables

### Unordered Lists

```markdown
- First item
- Second item
  - Nested item
  - Another nested item
- Third item
```

**Guidelines:**
- Use `-` for bullets (not `*` or `+`)
- Indent nested items with 2 spaces
- Leave blank line before and after list
- Use parallel structure for list items

### Ordered Lists

```markdown
1. First step
2. Second step
3. Third step
```

**Guidelines:**
- Always use `1.` for numbering (auto-increments)
- Use for sequential steps
- Include "Step" in text if needed for clarity

### Task Lists

```markdown
- [ ] Uncompleted task
- [x] Completed task
- [ ] Another task
```

**Guidelines:**
- Use for checklists
- Include in PR templates and guides
- Keep items concise and actionable

### Tables

```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1    | Data     | More     |
| Row 2    | Data     | More     |
```

**Guidelines:**
- Use for structured data
- Keep cells concise
- Align headers and dividers
- Include header row always

---

## Emojis

### When to Use Emojis

**Appropriate:**
- ✅ H1 document titles (one emoji, right side)
- ✅ Section markers for visual scanning
- ✅ Status indicators (✅ ❌ ⏳ 🟢 🟡 🔴)
- ✅ Callouts and highlights

**Not Appropriate:**
- ❌ Middle of sentences
- ❌ Multiple emojis in succession
- ❌ As replacement for words
- ❌ In code examples or technical content

### Common Emoji Usage

**Status:**
- ✅ Complete/Correct
- ❌ Incomplete/Incorrect
- ⏳ In Progress
- 🟢 Excellent/Green
- 🟡 Warning/Yellow
- 🔴 Error/Red

**Documentation:**
- 📝 Documentation
- 📚 Learning/Reference
- 🔧 Technical/Tools
- 🎨 Design/Creative
- 🌟 Special/Featured
- 💜 Community/Love

**Actions:**
- 🚀 Launch/Deploy
- 🔒 Security
- 🧪 Testing
- 📊 Metrics/Data
- 🎯 Goals/Targets
- 💡 Ideas/Tips

### Emoji Guidelines

**Do:**
- ✅ Use standard Unicode emojis
- ✅ Use sparingly for visual navigation
- ✅ Choose emojis with clear meaning
- ✅ Be consistent across docs

**Don't:**
- ❌ Overuse emojis
- ❌ Use obscure or ambiguous emojis
- ❌ Rely on emoji alone to convey meaning
- ❌ Use custom emoji graphics

---

## File Naming

### Documentation Files

**Pattern:** `UPPERCASE.md` for primary docs
```
CONTRIBUTING.md
ARCHITECTURE.md
README.md
```

**Pattern:** `lowercase.md` for supporting docs
```
manifest.json
package.json
.editorconfig
```

### Guidelines

**Do:**
- ✅ Use ALL_CAPS for primary documentation
- ✅ Use descriptive, clear names
- ✅ Use hyphens for multi-word names: `good-first-issue.md`
- ✅ Include `.md` extension for markdown

**Don't:**
- ❌ Use spaces in filenames
- ❌ Use special characters except hyphens and underscores
- ❌ Create ambiguous names
- ❌ Exceed ~30 characters if possible

---

## Special Formatting

### Callouts and Highlights

**Important Information:**
```markdown
**Important:** This is critical information.
```

**Notes:**
```markdown
**Note:** This is supplementary information.
```

**Tips:**
```markdown
💡 **Tip:** This is a helpful suggestion.
```

**Warnings:**
```markdown
⚠️ **Warning:** This requires caution.
```

### Blockquotes

**For Quotes:**
```markdown
> *"The gift must always move"* — Lewis Hyde
```

**For Emphasis:**
```markdown
> This project practices sacred reciprocity.
```

**Guidelines:**
- Use for actual quotes with attribution
- Use for document taglines/descriptions
- Use sparingly for emphasis
- Don't nest blockquotes unless necessary

### Horizontal Rules

```markdown
---
```

**Use for:**
- Major section breaks
- Before and after document footer
- Separating distinct content areas

**Don't use for:**
- Between every section
- Visual decoration without purpose
- Inside lists or tables

---

## Documentation Checklist

**Before Submitting Documentation:**

- [ ] Spell check completed (add new terms to `.wordlist.txt`)
- [ ] All links verified and working
- [ ] Cross-references added where helpful
- [ ] Code examples tested and working
- [ ] Follows style guide formatting
- [ ] Tone is warm and welcoming
- [ ] Terminology is consistent
- [ ] Structure includes required elements
- [ ] Updated INDEX.md if new file
- [ ] Updated PROJECT_STATUS.md if significant
- [ ] Added terms to GLOSSARY.md if needed
- [ ] PR uses documentation checklist

---

## Integration Requirements

### When Creating New Documentation

**Must Do:**
1. Add to [INDEX.md](INDEX.md) in appropriate section(s)
2. Add cross-references from related docs
3. Add to [PROJECT_STATUS.md](PROJECT_STATUS.md) if primary doc
4. Update `.wordlist.txt` with new terms
5. Update [CHANGELOG.md](CHANGELOG.md)

### When Updating Existing Documentation

**Should Do:**
1. Verify cross-references still accurate
2. Check for terminology consistency
3. Update modification notes if major changes
4. Consider updating related docs

---

## Examples of Excellent Documentation

**Study these for reference:**

**Well-Structured:**
- [CONTRIBUTING.md](CONTRIBUTING.md) - Clear sections, excellent flow
- [LEARNING_PATHS.md](LEARNING_PATHS.md) - Detailed, organized, scannable

**Great Tone:**
- [COMMUNITY.md](COMMUNITY.md) - Warm, welcoming, inclusive
- [VISION.md](VISION.md) - Inspiring, clear, purposeful

**Excellent Cross-Referencing:**
- [INDEX.md](INDEX.md) - Perfect navigation hub
- [EXAMPLES.md](EXAMPLES.md) - Well-linked patterns

**Technical Clarity:**
- [TESTING.md](TESTING.md) - Clear instructions, good examples
- [DEPLOYMENT.md](DEPLOYMENT.md) - Step-by-step, well-organized

---

## Getting Help with Documentation

**Questions about style?**
1. Check this guide first
2. Review similar documentation for patterns
3. Ask in [Discussions Q&A](https://github.com/Luminous-Dynamics/infin-love/discussions/categories/q-a)
4. Tag maintainers for guidance

**Found inconsistency?**
- Open an issue or PR to fix it
- Help us improve this guide
- Documentation contributions valued!

---

## Evolving This Guide

**This style guide evolves with the community.**

**Suggest improvements:**
- Open an issue with suggestions
- Submit a PR with enhancements
- Discuss in community forums
- Share examples of great documentation

---

<div align="center">

**Consistency creates clarity** 📝

**Clarity serves love** 💜

**Questions?** See [SUPPORT.md](SUPPORT.md) or [CONTRIBUTING.md](CONTRIBUTING.md)

Built with consciousness • Shared with love • Held in sacred reciprocity

[⬆ Back to Top](#documentation-style-guide-)

</div>
