---
title: "Documentation"
description: "Complete guide to Hugo SmartLink installation and configuration"
date: 2024-07-09
draft: false
weight: 1
---

# 📖 Hugo SmartLink Documentation

Complete guide to installing, configuring, and using Hugo SmartLink in your projects.

## 🚀 Quick Start

### Installation

1. **Add the module to your Hugo site:**
   ```bash
   hugo mod get github.com/qgp9/hugo-smartlink@latest
   ```

2. **Configure the module in your `hugo.toml`:**
   ```toml
   [module]
   [[module.imports]]
     path = "github.com/qgp9/hugo-smartlink"
   ```

3. **Add SmartLink configuration:**
   ```toml
   [params.modules.smartlink]
     output = "html"
     normalizeEscapedWikilink = true
   ```

### Basic Usage

Start using wiki links immediately in your content:

```markdown
# My Documentation

This is a link to [[my-page]] and another to [[about-us]].
```

**Output:**
```html
<p>This is a link to <a href="/my-page" class="wikilink">my-page</a> and another to <a href="/about-us" class="wikilink">about-us</a>.</p>
```

## ⚙️ Configuration

### Basic Configuration

```toml
[params.modules.smartlink]
  output = "html"  # "html" or "markdown"
  normalizeEscapedWikilink = true
```

### Advanced Configuration

```toml
[params.modules.smartlink]
  output = "html"
  normalizeEscapedWikilink = true
  
  # Prefix aliases
  [params.modules.smartlink.prefixAlias]
    "docs:" = "/documentation/"
    "~" = "/home/"
    "gh:" = "https://github.com/owner/repo/"
  
  # Custom patterns
  [[params.modules.smartlink.rules]]
    name = "JIRA Issue"
    pattern = "^([A-Z][A-Z0-9]+-[0-9]+)$"
    url = "https://company.atlassian.net/browse/{0}"
    class = "jira-link"
  
  [[params.modules.smartlink.rules]]
    name = "GitHub Issue"
    pattern = "^#([0-9]+)$"
    url = "https://github.com/owner/repo/issues/{1}"
    class = "github-issue"
  
  [[params.modules.smartlink.rules]]
    name = "WikiLink"
    wikiLink = true
    stripNamespace = true
    class = "wikilink"
  
  [[params.modules.smartlink.rules]]
    name = "Broken Link"
    pattern = "^.*$"
    url = "/broken-link/"
    class = "broken-link"
```

## 🎨 Customization

### Output Formats

**HTML Output (Default):**
```html
<a href="/page" class="wikilink">page</a>
```

**Markdown Output:**
```markdown
[page](/page)
```

### CSS Classes

Each link type gets a unique CSS class for styling:

```css
.wikilink { color: #0066cc; }
.jira-link { color: #0052cc; }
.github-issue { color: #24292e; }
.slack-channel { color: #4a154b; }
.email-link { color: #d93025; }
.broken-link { color: #dc3545; text-decoration: line-through; }
```

### Custom Labels

Use the pipe syntax for custom labels:

```markdown
[[page|Custom Label]]
```

## 🔧 Integration with Themes

### Content Partial Override

Most Hugo themes use a content partial. Override it to enable SmartLink:

```html
<!-- layouts/_default/_markup/render-content.html -->
{{ .Content | safeHTML }}
```

### Theme-Specific Integration

For themes that use custom content rendering, ensure SmartLink is applied to the content before rendering.

## 🚀 Best Practices

### Rule Order

SmartLink processes rules in order. Recommended sequence:

1. **Custom Patterns** (highest priority)
2. **Specific Wiki Links**
3. **General Wiki Links**
4. **Broken Link Fallback** (lowest priority)

### Performance

- Use specific patterns before general ones
- Limit the number of rules for better performance
- Consider caching for large sites

### Maintenance

- Regular pattern testing
- Monitor broken link reports
- Update external system URLs as needed

## 🐛 Troubleshooting

### Common Issues

**Links not converting:**
- Check if SmartLink module is properly installed
- Verify configuration syntax
- Ensure content is processed by SmartLink

**Wrong URLs generated:**
- Review pattern matching rules
- Check URL template syntax
- Verify prefix aliases

**Performance issues:**
- Reduce number of rules
- Use more specific patterns
- Consider caching strategies

### Debug Mode

Enable debug logging to troubleshoot:

```toml
[params.modules.smartlink]
  debug = true
```

## 📚 API Reference

### Configuration Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `output` | string | "html" | Output format ("html" or "markdown") |
| `normalizeEscapedWikilink` | boolean | true | Normalize escaped wiki links |
| `debug` | boolean | false | Enable debug logging |

### Rule Configuration

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `name` | string | Yes | Rule name for identification |
| `pattern` | string | No | Regex pattern for matching |
| `url` | string | No | URL template with placeholders |
| `class` | string | No | CSS class for styling |
| `wikiLink` | boolean | No | Enable wiki link processing |
| `stripNamespace` | boolean | No | Remove namespace from display |

### URL Placeholders

- `{0}` - Full matched text
- `{1}`, `{2}`, etc. - Captured groups

---

*For more examples and advanced usage, visit our [[examples]] section!* 