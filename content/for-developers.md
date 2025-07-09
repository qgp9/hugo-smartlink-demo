---
title: "For Theme Developers"
weight: 5
---

If you are a Hugo theme developer, you can ensure your theme is compatible with Hugo SmartLink by following a simple convention.

## The `content.html` Partial

To allow Hugo SmartLink to process the content of a page, your theme should render the content using a partial instead of the `{{ .Content }}` variable directly.

### Step 1: Create the Content Partial

Create a file at `layouts/_partials/content.html` with the following content:

```html
{{ .Content }}
```

### Step 2: Update Your Templates

In your page templates (e.g., `layouts/_default/single.html`, `layouts/_default/list.html`), replace any instances of `{{ .Content }}` with a call to the partial:

```go-template
{{ partial "content.html" . }}
```

By doing this, you create an override point. Hugo SmartLink provides its own `content.html` partial that intercepts the content, applies the SmartLink transformations, and then outputs the result.

This approach ensures that users of your theme can enable Hugo SmartLink without having to modify the theme files themselves, providing a seamless integration experience.
