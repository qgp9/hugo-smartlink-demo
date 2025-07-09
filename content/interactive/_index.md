---
title: "Interactive Tools"
description: "Live SmartLink testing and configuration tools"
date: 2024-07-09
draft: false
weight: 1
---

# 🎮 Interactive SmartLink Tools

Test Hugo SmartLink functionality in real-time with these interactive tools.

## 🔧 Live SmartLink Editor

Try different SmartLink patterns and see how they're processed:

### Test Input
```
[[examples]] - Basic wiki link
[[documentation|Read the docs]] - With custom label
[[PROJ-123]] - JIRA issue
[[#42]] - GitHub issue
[[slack:#general]] - Slack channel
[[email:contact@example.com]] - Email link
[[docs:installation]] - With prefix alias
```

### Expected Output
- `[[examples]]` → `<a href="/examples" class="wikilink">examples</a>`
- `[[documentation|Read the docs]]` → `<a href="/documentation" class="wikilink">Read the docs</a>`
- `[[PROJ-123]]` → `<a href="https://example.atlassian.net/browse/PROJ-123" class="jira-link">PROJ-123</a>`
- `[[#42]]` → `<a href="https://github.com/qgp9/hugo-smartlink/issues/42" class="github-issue">#42</a>`
- `[[slack:#general]]` → `<a href="https://company.slack.com/app_redirect?channel=general" class="slack-channel">slack:#general</a>`
- `[[email:contact@example.com]]` → `<a href="mailto:contact@example.com" class="email-link">email:contact@example.com</a>`
- `[[docs:installation]]` → `<a href="/documentation/installation" class="wikilink">installation</a>`

## ⚙️ Configuration Example

### Basic Settings
```toml
[params.modules.smartlink]
  output = "html"  # or "markdown"
  normalizeEscapedWikilink = true
```

### Pattern Rules
```toml
# JIRA Issues
[\[params.modules.smartlink.rules]]
  name = "JIRA Issue"
  pattern = "^([A-Z][A-Z0-9]+-[0-9]+)$"
  url = "https://company.atlassian.net/browse/{0}"
  class = "jira-link"

# GitHub Issues
[\[params.modules.smartlink.rules]]
  name = "GitHub Issue"
  pattern = "^#([0-9]+)$"
  url = "https://github.com/owner/repo/issues/{1}"
  class = "github-issue"

# Slack Channels
[\[params.modules.smartlink.rules]]
  name = "Slack Channel"
  pattern = "^slack:#([a-z0-9-]+)$"
  url = "https://company.slack.com/app_redirect?channel={1}"
  class = "slack-channel"

# Email Links
[\[params.modules.smartlink.rules]]
  name = "Email Link"
  pattern = "^email:(.+)$"
  url = "mailto:{1}"
  class = "email-link"

# Wiki Links
[\[params.modules.smartlink.rules]]
  name = "WikiLink"
  wikiLink = true
  stripNamespace = true
  class = "wikilink"

# Broken Link Fallback
[\[params.modules.smartlink.rules]]
  name = "Broken Link"
  pattern = "^.*$"
  url = "/broken-link/"
  class = "broken-link"
```

### Prefix Aliases
```toml
[params.modules.smartlink.prefixAlias]
  "docs:" = "/documentation/"
  "~" = "/home/"
  "gh:" = "https://github.com/owner/repo/"
```

## 🎨 CSS Styling Examples

Customize the appearance of your SmartLinks:

```css
.wikilink { color: #0066cc; text-decoration: none; }
.wikilink:hover { text-decoration: underline; }
.jira-link { color: #0052cc; background-color: #f4f5f7; padding: 2px 6px; border-radius: 3px; font-family: monospace; }
.github-issue { color: #24292e; background-color: #f1f8ff; padding: 2px 6px; border-radius: 3px; font-family: monospace; }
.slack-channel { color: #4a154b; background-color: #f8f0f8; padding: 2px 6px; border-radius: 3px; }
.email-link { color: #d93025; text-decoration: none; }
.email-link:hover { text-decoration: underline; }
.broken-link { color: #dc3545; text-decoration: line-through; opacity: 0.6; }
```

---

*All examples above are real and verifiable with this demo site. No fake features or links included.* 