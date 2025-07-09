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
- [[home]] - Link to homepage (created with `[[home]]`)
- [[documentation]] - Link to documentation section (created with `[[documentation]]`)
- [[interactive]] - Link to interactive tools (created with `[[interactive]]`)

### With Custom Labels
- [[examples|See more examples]] - Link with custom label (created with `[[examples|See more examples]]`)
- [[documentation|Read the docs]] - Another custom label example (created with `[[documentation|Read the docs]]`)

## 🏢 External System Integration

SmartLink can integrate with various external systems and tools:

### JIRA Issues
- [[PROJ-123]] - Project issue (created with `[[PROJ-123]]`)
- [[BUG-456]] - Bug report (created with `[[BUG-456]]`)
- [[FEAT-789]] - Feature request (created with `[[FEAT-789]]`)

{{% notice title="Configuration" expanded="false" %}}
```toml
[[params.modules.smartlink.rules]]
   name = "JIRA Issue"
   pattern = "^([A-Z][A-Z0-9]+-[0-9]+)$"
   url = "https://example.atlassian.net/browse/{0}"
   class = "jira-link"
```
{{% /notice %}}

### GitHub Integration
- [[#42]] - GitHub issue (created with `[[#42]]`)
- [[PR#15]] - Pull request (created with `[[PR#15]]`)
- [[gh:issues/42]] - Using prefix alias (created with `[[gh:issues/42]]`)
- [[https://github.com/qgp9/hugo-smartlink/issues/123]] - Displays as 'qgp9/hugo-smartlink#123' (created with `[[https://github.com/qgp9/hugo-smartlink/issues/123]]`)

{{% notice title="Configuration" expanded="false" %}}
```toml
[[params.modules.smartlink.rules]]
  name = "GitHub Issue"
  pattern = "^#([0-9]+)$"
  url = "https://github.com/qgp9/hugo-smartlink/issues/{1}"
  class = "github-issue"

[[params.modules.smartlink.rules]]
  name = "GitHub PR"
  pattern = "^PR#([0-9]+)$"
  url = "https://github.com/qgp9/hugo-smartlink/pull/{1}"
  class = "github-pr"

[[params.modules.smartlink.rules]]
  name = "GitHub Issue URL Shortener"
  pattern = "^https:\/\/github\.com\/([^/]+)\/([^/]+)\/issues\/(\d+)$"
  label = "{1}/{2}#{3}"
  class = "github-url-shortener"
```
{{% /notice %}}

### Communication Tools
- [[slack:#general]] - Slack channel (created with `[[slack:#general]]`)
- [[slack:#random]] - Another Slack channel (created with `[[slack:#random]]`)
- [[email:team@company.com]] - Email link (created with `[[email:team@company.com]]`)

{{% notice title="Configuration" expanded="false" %}}
```toml
[[params.modules.smartlink.rules]]
  name = "Slack Channel"
  pattern = "^slack:#([a-z0-9-]+)$"
  url = "https://company.slack.com/app_redirect?channel={1}"
  class = "slack-channel"

[[params.modules.smartlink.rules]]
  name = "Email Link"
  pattern = "^email:(.+)$"
  url = "mailto:{1}"
  class = "email-link"
```
{{% /notice %}}

## 📁 Prefix Aliases

Map namespace prefixes to different paths:

{{% notice title="Configuration" expanded="false" %}}
```toml
[params.modules.smartlink.prefixAlias]
  "docs:" = "/documentation/"
  "~" = "/home/"
  "gh:" = "https://github.com/qgp9/hugo-smartlink/"
  "user:" = "/users/"
```
{{% /notice %}}

### Documentation Prefix
- [[docs:installation]] - Maps to `/documentation/installation` (created with `[[docs:installation]]`)
- [[docs:configuration]] - Maps to `/documentation/configuration` (created with `[[docs:configuration]]`)
- [[docs:examples]] - Maps to `/documentation/examples` (created with `[[docs:examples]]`)

### Home Prefix
- [[~home]] - Maps to `/home/` (created with `[[~home]]`)
- [[~about]] - Maps to `/home/about` (created with `[[~about]]`)

### GitHub Prefix
- [[gh:issues/42]] - Maps to GitHub issues (created with `[[gh:issues/42]]`)
- [[gh:pull/15]] - Maps to GitHub pull requests (created with `[[gh:pull/15]]`)

## 🎨 Advanced Patterns

### Custom Pattern Matching
- [[ISBN:978-0-7475-3269-9]] - Book reference (created with `[[ISBN:978-0-7475-3269-9]]`)
- [[ISBN:978-0-7475-3269-9|Harry Potter]] - With custom label (created with `[[ISBN:978-0-7475-3269-9|Harry Potter]]`)

### Complex URL Patterns
- [[api:/users/{id}|User API]] - API documentation (created with `[[api:/users/{id}|User API]]`)
- [[docs:guides/getting-started|Getting Started]] - Nested documentation (created with `[[docs:guides/getting-started|Getting Started]]`)

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
- [[installation]] - Installation guide (created with `[[installation]]`)
- [[configuration]] - Configuration options (created with `[[configuration]]`)
- [[troubleshooting]] - Common issues (created with `[[troubleshooting]]`)
- [[api-reference]] - API documentation (created with `[[api-reference]]`)

### Project Management
- [[PROJ-123]] - Current sprint task (created with `[[PROJ-123]]`)
- [[#42]] - Related GitHub issue (created with `[[#42]]`)
- [[slack:#project-updates]] - Team updates (created with `[[slack:#project-updates]]`)

### Knowledge Base
- [[faq]] - Frequently asked questions (created with `[[faq]]`)
- [[tutorials]] - Step-by-step guides (created with `[[tutorials]]`)
- [[reference]] - Quick reference (created with `[[reference]]`)

---

*All these examples demonstrate the power and flexibility of Hugo SmartLink. Try clicking on any link to see how they work!* 
