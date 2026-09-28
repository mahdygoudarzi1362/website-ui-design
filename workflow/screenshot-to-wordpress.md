# Screenshot to WordPress UI Workflow

## 1. Reference
Collect the screenshot, visual reference, Figma frame, or approved design.

## 2. UI analysis
Identify layout, hierarchy, spacing, typography, colors, components, assets, interactions, and responsive behavior before generating code.

## 3. Prototype
Use Screenshot-to-Code to produce a visual prototype. Treat generated code as a starting point.

## 4. Clean and review
Remove unnecessary code, verify semantics, assets, responsiveness, accessibility basics, and browser behavior.

## 5. WordPress adaptation
Inspect the target theme, builder, existing global styles, fonts, breakpoints, plugins, and available components. Adapt the prototype to the actual environment instead of blindly pasting generated code.

## 6. CSS/JS isolation
Wrap the feature in a unique namespace. Avoid global selectors and global JavaScript unless explicitly required.

## 7. Responsive implementation
Validate desktop, tablet, and mobile behavior. Check layout, typography, buttons, images, overflow, and spacing.

## 8. Real-site installation
Implement on the actual destination site.

## 9. Visual QA
Capture the installed result at the same relevant viewport sizes as the reference.

## 10. Compare and refine
Record differences, fix them in priority order, capture a new screenshot, and repeat until the agreed visual quality is reached.

The destination website does not need to be connected to GitHub. This repository stores the reusable process and project documentation.