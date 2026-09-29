# Astro

Source: [withastro/astro](https://github.com/withastro/astro)

## Role in this system

Astro is an implementation option for content-heavy websites and marketing experiences where most of the page can remain lightweight and static, while interactive components can be added where needed.

The repository is a **framework reference**, not a requirement to use Astro.

## Reusable principles

- Select the framework from the product's rendering and interaction requirements, not from visual preference.
- For content-heavy pages, prefer a lightweight rendering strategy when it meets the requirements.
- Keep interactive behavior scoped to the parts that actually need client-side behavior.
- Treat framework integrations (React, Vue, Node, deployment adapters, sitemap, MDX, etc.) as explicit technical choices.
- Verify the current Astro version and integration APIs in the real project environment before implementation.
- Browser QA and visual QA remain mandatory; framework choice does not replace them.

## When to use

Consider Astro for marketing sites, documentation, blogs, landing pages, and other content-heavy experiences where limited interactivity and lightweight output are important.

Last reviewed: 2026-09-29
