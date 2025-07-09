---
title: "Configuration"
weight: 2
---

Hugo SmartLink offers a flexible configuration system to tailor its behavior to your needs. You can customize everything from the output format to complex link patterns.

All configuration is done within your `hugo.toml` file under the `[params.modules.smartlink]` section.

## Basic Configuration

Here is an example of a basic configuration:

```toml
[params]
  [params.modules]
    [params.modules.smartlink]
      output = "html"  # "html" (default) or "markdown"
      normalizeEscapedWikilink = true  # Normalize escaped wiki links for documentation
      [params.modules.smartlink.prefixAlias]
        "~" = "/doc/"
        "docs:" = "/documentation/"
```

### Output Format

You can control how wiki links are rendered.

- **`html`** (Default): Renders links as raw HTML `<a>` tags. This is faster and allows for direct CSS class application.
- **`markdown`**: Renders links as standard Markdown links, which are then processed by Hugo's rendering engine. This is useful if you have custom link render hooks.

### Prefix Aliases

Prefix aliases allow you to map a prefix to a specific path. For example, `[[~/my-page]]` can be configured to link to `/docs/my-page`.

**Example:**
```toml
[params.modules.smartlink.prefixAlias]
  "~" = "/doc/"
  "docs:" = "/documentation/"
```

- `[\[~/About]]` becomes `[\[/doc/About]]` -> [[~/About]]
- `[\[docs:Guide]]` becomes `[\[/documentation/Guide]]` -> [[docs:Guide]]

## Advanced Configuration: Rules

The real power of Hugo SmartLink lies in its rule-based system. You can define a series of rules to handle different types of links. Rules are processed in the order they are defined.

**Recommended Rule Order:**
1.  **Custom Patterns**: For external systems like JIRA or GitHub.
2.  **WikiLinks**: For internal page links.
3.  **Broken Link Fallback**: A catch-all for any links that don't match other rules.

### Example: JIRA and GitHub Integration

```toml
[[params.modules.smartlink.rules]]
  name = "JIRA"
  pattern = "^([A-Z][A-Z0-9]+-\d+)$"
  url = "https://example.com/browse/{0}"
  class = "jira-link"

[[params.modules.smartlink.rules]]
  name = "GitHub Issue"
  pattern = "^#(\d+)$"
  url = "https://github.com/owner/repo/issues/{1}"
  class = "github-issue"
```

With this configuration:
- `[\[PROJ-123]]` will link to the JIRA issue.
- `[\[#42]]` will link to the GitHub issue.

See the [[examples]] page for a live demonstration of these rules.
