---
title: Test3
smartlink:
  usePageTitle: false
  usePageTitlePrefixes: ["docs:", "-@", "-+"]

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
  usePageTitlePrefixes: ["docs:", "-@", "-+"]
```
