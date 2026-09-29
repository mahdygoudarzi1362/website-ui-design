# Context7

Official project: https://github.com/upstash/context7

Context7 provides current, version-specific documentation and code examples for libraries and APIs. In this repository it is a **development reference**, not a UI component or production dependency.

## Why it belongs in this workflow

UI implementation often depends on libraries, frameworks, icon systems, charting tools, animation libraries, or WordPress integrations whose APIs change over time. Generated code can otherwise rely on outdated examples or APIs that no longer exist.

Use Context7 when the implementation depends on a library/API and the current documentation matters.

## Usage rule

Before writing library-specific production code:

1. Identify the exact library/framework and, when relevant, its version.
2. Resolve the library to its Context7 library ID when possible.
3. Query the documentation for the exact task being implemented.
4. Prefer documented current APIs and examples over model memory or old snippets.
5. Review the result against the target project's actual environment before implementation.

Example prompt pattern:

```text
Implement [specific UI/library task].
Use Context7 for the current [library] documentation.
Use library [Context7 library ID] when known.
```

## Version awareness

If a project pins a library version, explicitly request that version's documentation. Do not silently use examples from a newer major version.

## What Context7 does not replace

Context7 does not replace:

- visual analysis of the reference
- Screenshot-to-Code prototyping
- code review and cleanup
- CSS/JS isolation
- responsive QA
- real-site testing
- visual comparison

It strengthens the implementation stage by making library/API knowledge current.

## Security

Do not commit Context7 API keys or other credentials to this repository.