# CSS Isolation Guidelines

## Goal

Prevent a new UI component from changing unrelated parts of the website.

## Namespace

Give every component or page section a unique root namespace.

Example:

```css
.mhd-pricing {}
.mhd-pricing__card {}
.mhd-pricing__title {}
.mhd-pricing__button {}
```

## Avoid

- Global `body`, `html`, `h1`, `p`, `a`, or generic element styling unless explicitly required.
- Generic class names such as `.card`, `.title`, `.button`, or `.container`.
- Unnecessary `!important`.
- Global CSS variables that can overwrite the site's existing variables.
- Global JavaScript selectors or event handlers.

## Required checks

After implementation, verify that:

1. The new component renders correctly.
2. Existing header, footer, navigation, forms, and unrelated components are unchanged.
3. Theme/plugin styles do not unexpectedly override the component.
4. Component styles do not leak into the rest of the site.