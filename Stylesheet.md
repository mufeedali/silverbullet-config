---
tags:
- meta
- space-styles
---

# Base Theme

```space-style
html[data-theme="dark"] {
  --editor-code-background-color: var(--editor-frontmatter-background-color);
  --editor-border-color: #656565;
}

#sb-main .cm-scroller {
  padding-top: 8px;
}

#sb-main .cm-editor .cm-line {
  line-height: 1.6;
}
```

# Table of Contents & Linked Mentions

```space-style
#sb-main .cm-editor .sb-markdown-top-widget:has(*),
#sb-main .cm-editor .sb-markdown-bottom-widget:has(*) {
  overflow: hidden;
  border-radius: 4px;
  border: 1px solid var(--editor-border-color);
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.35);
}

#sb-main .cm-editor .sb-markdown-top-widget:has(*) .content > ul,
#sb-main .cm-editor .sb-markdown-bottom-widget:has(*) .content > ul {
  padding-top: 8px;
  padding-bottom: 8px;
}

#sb-main .cm-editor .sb-markdown-top-widget:has(*) h1,
#sb-main .cm-editor .sb-markdown-bottom-widget:has(*) h1 {
  padding-left: 16px !important;
  padding-right: 16px !important;
  border-bottom: 1px solid var(--editor-border-color);
}
```

# Code Blocks

> **note** Note
> Also applies the same styling for frontmatter.

> **warning** Warning
> There is a bug in the shadows where there is a gap between the shadows of each line.

```space-style
div:not(.sb-line-fenced-code)
  + .sb-line-fenced-code:not(.sb-fenced-code-iframe, .sb-fenced-code-hide),
div:not(.sb-frontmatter) + .sb-frontmatter:not(.cm-line > .sb-frontmatter) {
  padding-top: 4px !important;
  border-top: 1px solid var(--editor-border-color);
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
}

#sb-main .cm-editor .cm-line.sb-line-fenced-code.sb-line-ul,
#sb-main .cm-editor .cm-line.sb-line-fenced-code.sb-line-ol {
  /* padding-left: 8px;
  padding-right: 8px; */
  border-left: 1px solid var(--editor-border-color);
  border-right: 1px solid var(--editor-border-color);
  box-shadow: -5px 0 5px -5px rgba(0, 0, 0, 0.35),
    5px 0 5px -5px rgba(0, 0, 0, 0.35);
}

#sb-main .cm-editor .cm-line.sb-line-fenced-code:not(.sb-fenced-code-iframe, .sb-fenced-code-hide, .sb-line-ul, .sb-line-ol),
.sb-frontmatter:not(.cm-line > .sb-frontmatter) {
  padding-left: 8px !important;
  padding-right: 8px !important;
  border-left: 1px solid var(--editor-border-color);
  border-right: 1px solid var(--editor-border-color);
  box-shadow: -5px 0 5px -5px rgba(0, 0, 0, 0.35),
    5px 0 5px -5px rgba(0, 0, 0, 0.35);
}

#sb-main .cm-editor .cm-line.sb-line-fenced-code:not(.sb-fenced-code-hide):has(
    + :not(.sb-line-fenced-code)
  ),
.sb-frontmatter:not(.cm-line > .sb-frontmatter):has(+ :not(.sb-frontmatter)) {
  padding-bottom: 4px !important;
  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
  border-bottom: 1px solid var(--editor-border-color);
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.35); /* Right and bottom shadow */
}
```

# Inline Code

```space-style
.sb-code:not(.sb-line-fenced-code .sb-code, .sb-line-code .sb-code) {
  padding-right: 5px;
  padding-left: 5px;
  border: 1px solid var(--editor-border-color);
  border-radius: 4px;
  box-shadow: 0px 0px 4px 0px rgba(0, 0, 0, 0.35);
}
```

Test: `test`

# Non-Monospace Font

> **warning** Warning
> Does not work as expected right now because all indentations in SilverBullet are hard-coded. Currently set to `css` instead of `space-script` so that it’s disabled.

```css
@import url("https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap");

html[data-theme="dark"] {
  --editor-font: "Inter" !important;
  --editor-mono-font: "iA-Mono", "Menlo" !important;
}

#sb-editor .sb-code,
#sb-editor .sb-line-fenced-code,
#sb-editor .sb-frontmatter {
  font-family: var(--editor-mono-font);
}
```

# Admonitions Styling

```space-style
.sb-admonition {
  border-right: 1px solid var(--editor-border-color);
  box-shadow: -5px 0 5px -5px rgba(0, 0, 0, 0.35),
    5px 0 5px -5px rgba(0, 0, 0, 0.35);
}

.sb-admonition-title {
  border-top: 1px solid var(--editor-border-color);
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
}

.sb-admonition:has(+ :not(.sb-admonition)) {
  padding-bottom: 4px !important;
  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
  border-bottom: 1px solid var(--editor-border-color);
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.35); /* Right and bottom shadow */
}
```

## Test

> **note** This is a
> note admonition

> **warning** This is a
> warning admonition

# Dark Mode Search Fix

```space-style
.cm-search .cm-button {
  background-image: none;
}

.cm-search .cm-textfield {
  background-color: var(--panel-background-color);
}
```

# Quote Styling

```space-style
.sb-blockquote-outside {
  padding-left: 8px !important;
  padding-right: 8px !important;
}
```

# Command Buttons

```space-style
.sb-command-button {
  box-shadow: 0px 8px 8px rgba(0, 0, 0, 0.35);
}
```

# Non-Table Markdown Widgets

```space-style
.sb-markdown-widget:not(:has(table)) {
  padding: 8px;
}
```

# Inline Frontmatter

> **warning** Warning
> Not using shadows here as the gap can look especially weird inline and the gaps seem unavoidable in this case.

```space-style
span:not(.cm-line > .sb-frontmatter) + :is(.cm-line > .sb-frontmatter),
.cm-line > .sb-frontmatter:first-child {
  border-left: 1px solid var(--editor-border-color);
  border-top-left-radius: 4px;
  border-bottom-left-radius: 4px;
}

.cm-line > .sb-frontmatter {
  border-top: 1px solid var(--editor-border-color);
  border-bottom: 1px solid var(--editor-border-color);
}

.cm-line > .sb-frontmatter:has(+ :not(.cm-line > .sb-frontmatter)),
.cm-line > .sb-frontmatter:last-child {
  border-right: 1px solid var(--editor-border-color);
  border-top-right-radius: 4px;
  border-bottom-right-radius: 4px;
}
```