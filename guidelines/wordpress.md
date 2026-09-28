# WordPress Implementation Guidelines

Before implementation, inspect:

- Theme and child theme
- Page builder (if any)
- Existing global CSS
- Existing global JavaScript
- Typography and font loading
- Breakpoints
- Existing reusable components
- Relevant plugins
- Header, footer, and container rules

## Integration rules

- Prefer the target site's existing design system where appropriate.
- Do not assume the generated prototype can be pasted directly into production.
- Avoid generic class names that may collide with the theme or plugins.
- Keep JavaScript scoped to the feature.
- Verify all assets and font dependencies.
- Check builder-specific markup and rendering behavior.
- Test the result on the real site, not only in the prototype environment.

## Supported environments

This workflow can be adapted to Elementor, Kadence, Gutenberg, Flatsome, and custom WordPress implementations.