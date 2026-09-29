# Tailwind CSS

Source: [tailwindlabs/tailwindcss](https://github.com/tailwindlabs/tailwindcss)

## Role in this system

Tailwind CSS is a utility-first CSS implementation option for building custom interfaces.

The repository is a **CSS implementation reference**, not a requirement to use Tailwind.

## Reusable principles

- Treat utility classes as an implementation mechanism, not as the design system itself.
- Define a coherent spacing, typography, color, radius, and responsive system before scattering one-off values.
- Keep semantic visual roles consistent across components.
- Reuse established project tokens/utilities instead of creating near-duplicate values.
- Avoid utility-heavy markup that obscures structure or makes component behavior difficult to understand.
- Verify the exact Tailwind version and configuration model before implementation.
- Keep accessibility, responsive behavior, and browser/visual QA independent of the CSS framework.

## When to use

Use this reference when a project already uses Tailwind or when utility-first CSS is an intentional implementation choice.

Last reviewed: 2026-09-29
