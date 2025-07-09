---
title: "SmartLink Examples"
description: "Comprehensive examples of Hugo SmartLink functionality"
date: 2024-07-09
draft: false
weight: 1
---

# 📚 SmartLink Examples

Explore the full range of Hugo SmartLink capabilities through these comprehensive examples.

## 🔗 Basic Wiki Links

The most common use case - simple wiki-style links that connect your content:

### Internal Page Links
- [[home]] - Link to homepage
- [[documentation]] - Link to documentation section
- [[interactive]] - Link to interactive tools

### With Custom Labels
- [[examples|See more examples]] - Link with custom label
- [[documentation|Read the docs]] - Another custom label example

## 🏢 External System Integration

SmartLink can integrate with various external systems and tools:

### JIRA Issues
- [[PROJ-123]] - Project issue
- [[BUG-456]] - Bug report
- [[FEAT-789]] - Feature request

### GitHub Integration
- [[#42]] - GitHub issue
- [[PR#15]] - Pull request
- [[gh:issues/42]] - Using prefix alias

### Communication Tools
- [[slack:#general]] - Slack channel
- [[slack:#random]] - Another Slack channel
- [[email:team@company.com]] - Email link

## 📁 Prefix Aliases

Map namespace prefixes to different paths:

### Documentation Prefix
- [[docs:installation]] - Maps to `/documentation/installation`
- [[docs:configuration]] - Maps to `/documentation/configuration`
- [[docs:examples]] - Maps to `/documentation/examples`

### Home Prefix
- [[~home]] - Maps to `/home/`
- [[~about]] - Maps to `/home/about`

### GitHub Prefix
- [[gh:issues/42]] - Maps to GitHub issues
- [[gh:pull/15]] - Maps to GitHub pull requests

## 🎨 Advanced Patterns

### Custom Pattern Matching
- [[ISBN:978-0-7475-3269-9]] - Book reference
- [[ISBN:978-0-7475-3269-9|Harry Potter]] - With custom label

### Complex URL Patterns
- [[api:/users/{id}|User API]] - API documentation
- [[docs:guides/getting-started|Getting Started]] - Nested documentation

## 🔧 Configuration Examples

### Different Output Formats

**HTML Output (Default):**
```html
<a href="/examples" class="wikilink">examples</a>
```

**Markdown Output:**
```markdown
[examples](/examples)
```

### Custom CSS Classes
Each link type gets its own CSS class for styling:
- `.wikilink` - Basic wiki links
- `.jira-link` - JIRA issues
- `.github-issue` - GitHub issues
- `.slack-channel` - Slack channels
- `.email-link` - Email links

## 🚀 Real-World Scenarios

### Documentation Site
- [[installation]] - Installation guide
- [[configuration]] - Configuration options
- [[troubleshooting]] - Common issues
- [[api-reference]] - API documentation

### Project Management
- [[PROJ-123]] - Current sprint task
- [[#42]] - Related GitHub issue
- [[slack:#project-updates]] - Team updates

### Knowledge Base
- [[faq]] - Frequently asked questions
- [[tutorials]] - Step-by-step guides
- [[reference]] - Quick reference

---

*All these examples demonstrate the power and flexibility of Hugo SmartLink. Try clicking on any link to see how they work!* 