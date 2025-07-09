---
title: "Hugo SmartLink Demo"
---


This site demonstrates the features of the **Hugo SmartLink** module, a powerful tool for adding wiki-style link functionality to your Hugo static site.

Explore the sections to learn how to install, configure, and use Hugo SmartLink in your own projects.

Here are some examples of what you can do:

- Link to another page: [[getting-started]]. This is created using the syntax `[\[getting-started]]`.
- Hugo SmartLink is case-insensitive by default, so [[Getting Started]] works too (created with `[\[Getting Started]]`).

## Explore the Documentation

- **[[getting-started]]**: Learn how to install and quickly start using the module.
- **[[configuration]]**: Dive into the various configuration options available.
- **[[examples]]**: See live examples of different link types and patterns.
- **[[performance]]**: Understand the performance characteristics of the module.
- **[[for-developers]]**: Find guidance for integrating SmartLink into your own themes.

{{% notice style="green" title="Raw Syntax" expanded="true" %}}
- **[\\[getting-started]]**: Learn how to install and quickly start using the module.
- **[\\[configuration]]**: Dive into the various configuration options available.
- **[\\[examples]]**: See live examples of different link types and patterns.
- **[\\[performance]]**: Understand the performance characteristics of the module.
- **[\\[for-developers]]**: Find guidance for integrating SmartLink into your own themes.
{{% /notice %}}

## Raw Syntax Example

You can display the raw `[[wikilink]]` syntax in your documentation by escaping it, like this:

```markdown
This is the raw syntax: [[my-page]]
```

This is the raw syntax: [[my-page]]

Which renders as:

{{% notice style="green" title="Raw Syntax" expanded="true" %}}
This is the raw syntax: [\\[my-page]]
{{% /notice %}}
