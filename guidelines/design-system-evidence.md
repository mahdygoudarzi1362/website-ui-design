# Design System Evidence

## Goal

Keep the repository's UI decisions grounded in evidence instead of turning accidental implementation details into design rules.

## When documenting a design system

Use DESIGN.md for a coherent product or website when persistent design context will help future implementation.

Document only decisions that are supported by:

- explicit product/design guidance
- named shared tokens
- shared primitives or variants
- repeated rendered evidence across relevant surfaces

Do not promote a one-off component value into a global token.

## Repository evidence

When source code is available, inspect in this order:

1. existing DESIGN.md and explicit guidance
2. tokens, themes, variables, and global styles
3. shared primitives and variants
4. representative routes and their consumers
5. local surface implementations

Trace the actual rendered path. Similar names or nearby files do not prove that two systems are connected.

## Screenshot or live-site evidence

A screenshot can establish visual intent but should not be treated as proof of an exact token value.

For exact values, prefer:

- computed styles
- loaded CSS declarations
- repeated values for the same role across representative pages

Do not invent semantic token names from raw values.

## DESIGN.md rules

When a project uses DESIGN.md:

- keep it small and focused on governing design language
- preserve existing accepted decisions unless current evidence replaces them
- keep exact normative values in its defined token structure
- keep implementation guidance in Markdown sections
- omit uncertain or page-local rules
- validate the document before treating it as authoritative

## Review rule

Before reporting a design-system violation, prove:

1. Contract — a rule or direct contradiction exists.
2. Runtime — that rule/owner actually reaches the affected surface.
3. Correction — one deterministic correction follows from the evidence.

If any proof is missing, report it as an observation or omit it; do not present it as a confirmed design-system problem.
