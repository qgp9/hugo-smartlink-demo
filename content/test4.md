---
title: Test4
smartlink:
  usePageTitle: false
  rules0:
    - name: "docs:"
      prefix: "docs:"
      url: "{0}"
      label: "{0}"
      usePageTitle: true
    - name: "@"
      prefix: "@"
      url: "{1}"
      label: "{1}"
      usePageTitle: true
    - name: "+"
      prefix: "+"
      url: "{1}"
      label: "{1}"
      usePageTitle: true
---

| raw | smartlink |
| --- | --- |
| `[[getting-started.md]]` | [[getting-started.md]] |
| `[[getting-started/index.md]]` | [[getting-started/index.md]] |
| `[[@getting-started/_index.md]]` | [[@getting-started/_index.md]] |
| `[[docs:configuration.md]]` | [[docs:configuration.md]] |
| `[[docs:configuration]]` | [[docs:configuration]] |
| `[[user:admin]]` | [[user:admin]] |
| `[[@user:admin]]` | [[@user:admin]] |
| `[[+user:admin]]` | [[+user:admin]] |
| `[[$user:admin]]` | [[$user:admin]] |

```yaml
smartlink:
  usePageTitle: false
  rules0:
    - name: "docs:"
      prefix: "docs:"
      url: "{0}"
      label: "{0}"
      usePageTitle: true
    - name: "@"
      prefix: "@"
      url: "{1}"
      label: "{1}"
      usePageTitle: true
    - name: "+"
      prefix: "+"
      url: "{1}"
      label: "{1}"
      usePageTitle: true
```