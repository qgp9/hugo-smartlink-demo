---
title: "Getting Started"
weight: 1
---

This guide will walk you through the installation and basic usage of the Hugo SmartLink module.

## Installation

Getting Hugo SmartLink up and running in your project is a two-step process.

### Step 1: Install the Module

Run the following command in your Hugo project's root directory to add the module:

```bash
hugo mod get github.com/qgp9/hugo-smartlink@latest
```

### Step 2: Add to Site Configuration

Add the module to your `hugo.toml` file to enable it:

```toml
[module]
[[module.imports]]
  path = "github.com/qgp9/hugo-smartlink"
```

## Quick Start

### Zero Configuration

Hugo SmartLink is designed to work out of the box with sensible defaults. Once installed, you can immediately start using `[[wikilink]]` syntax in your content without any further configuration.

### Basic Usage

Simply use the `[[wikilink]]` syntax in your Markdown files to create links to other pages.

For example, creating a link to a page named `my-awesome-page.md` is as simple as this:

**Markdown Input:**
```markdown
Check out [[my-awesome-page]] for more details.
```

**Rendered HTML Output:**
```html
<p>Check out <a href="/my-awesome-page" class="wikilink">my-awesome-page</a> for more details.</p>
```

As you can see, `[[my-awesome-page]]` is automatically converted into a valid HTML link. You can also see this in action on the [[examples]] page.
