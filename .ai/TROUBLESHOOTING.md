# Troubleshooting Guide

## Critical Issues

### Module Import Order Issue

**Problem**: SmartLink not processing content correctly with themes

**Symptoms**:
- `[[wikilink]]` syntax not converted to HTML links
- Links showing as plain text instead of clickable links
- No SmartLink classes appearing in generated HTML

**Root Cause**: Module import order in `hugo.toml`

**Solution**: SmartLink module MUST be imported BEFORE theme modules

```toml
[module]
# ✅ CORRECT ORDER
[[module.imports]]
  path = "github.com/qgp9/hugo-smartlink"  # SmartLink FIRST
[[module.imports]]
  path = "github.com/McShelby/hugo-theme-relearn"  # Theme SECOND

# ❌ WRONG ORDER
[[module.imports]]
  path = "github.com/McShelby/hugo-theme-relearn"  # Theme FIRST
[[module.imports]]
  path = "github.com/qgp9/hugo-smartlink"  # SmartLink SECOND
```

**Why**: Hugo processes modules in order, and SmartLink needs to process content before theme rendering.

### Verification

To verify SmartLink is working:

1. **Check generated HTML**:
   ```bash
   grep -r "class=wikilink\|class=broken-link" public/
   ```

2. **Look for SmartLink classes**:
   - `.wikilink` - Basic wiki links
   - `.jira-link` - JIRA issues  
   - `.github-issue` - GitHub issues
   - `.broken-link` - Unmatched patterns

3. **Test patterns**:
   - `[[examples]]` → `<a href="/examples" class="wikilink">examples</a>`
   - `[[#42]]` → `<a href="#42" class="wikilink">#42</a>`

## Common Issues

### Links Not Converting

**Check**:
1. Module import order in `hugo.toml`
2. SmartLink configuration in `params.modules.smartlink`
3. Content syntax: `[[link]]` not `[link]`

### Wrong URLs Generated

**Check**:
1. Pattern matching rules
2. URL template syntax with placeholders
3. Prefix alias configuration

### Performance Issues

**Solutions**:
1. Order rules by specificity (most specific first)
2. Limit number of rules (< 20 recommended)
3. Use efficient regex patterns
4. Enable caching for large sites

## Debug Mode

Enable debug logging:

```toml
[params.modules.smartlink]
  debug = true
```

This will show SmartLink processing in Hugo logs.

---

**Remember**: Module import order is CRITICAL for SmartLink to work with themes! 