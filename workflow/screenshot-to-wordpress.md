# Screenshot to WordPress UI Workflow

## 1. Reference
Collect the screenshot, visual reference, Figma frame, or approved design.

## 2. UI analysis
Identify layout, hierarchy, spacing, typography, colors, components, assets, interactions, and responsive behavior before generating code.

## 3. Prototype
Use Screenshot-to-Code to produce a visual prototype. Treat generated code as a starting point.

## 4. Current library/API verification
If the implementation uses a framework, UI library, charting library, icon library, animation library, API, or other versioned dependency, verify the current documentation with Context7 before relying on library-specific APIs or examples. Record the relevant version when the project pins one. Do not treat Context7 output as a substitute for reviewing the target environment.

See references/context7.md.

## 5. UI baseline and evidence review
Apply the focused UI quality checks before production adaptation:
- visual hierarchy, spacing, typography, data alignment, loading/empty states
- operational states when the UI contains live or asynchronous data
- summary/detail/count consistency for data-heavy surfaces
- accessibility basics such as keyboard/focus behavior and accessible names
- motion performance when animation exists
- evidence-based design-system decisions; do not promote local implementation details into global rules

Use guidelines/ui-quality.md, guidelines/operational-data-ui.md, guidelines/design-system-evidence.md, and guidelines/dashboard-ui.md. For focused task-specific guidance, see references/ui-skills.md, references/strix.md, and references/supabase.md.

## 6. Clean and review
Remove unnecessary code, verify semantics, assets, responsiveness, accessibility basics, browser behavior, and runtime state handling.

## 7. WordPress adaptation
Inspect the target theme, builder, existing global styles, fonts, breakpoints, plugins, and available components. Adapt the prototype to the actual environment instead of blindly pasting generated code.

## 8. CSS/JS isolation
Wrap the feature in a unique namespace. Avoid global selectors and global JavaScript unless explicitly required.

## 9. Responsive implementation
Validate desktop, tablet, and mobile behavior. Check layout, typography, buttons, images, overflow, spacing, fixed elements, and mobile interaction behavior.

## 10. Real-site installation
Implement on the actual destination site.

## 11. Visual QA
Capture the installed result at the same relevant viewport sizes as the reference.

## 12. Compare and refine
Record differences, fix them in priority order, capture a new screenshot, and repeat until the agreed visual quality is reached.

The destination website does not need to be connected to GitHub. This repository stores the reusable process and project documentation.
