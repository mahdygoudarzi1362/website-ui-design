# Playwright CLI Reference

Official project: https://github.com/microsoft/playwright-cli

## Role in this repository

Playwright CLI is a browser-execution and visual-QA reference. It is useful after implementation to inspect the real rendered page, exercise interactions, capture screenshots, inspect runtime state, and collect evidence for visual comparison.

It complements the other references:
- Screenshot-to-Code: visual prototype generation
- Context7: current library/API documentation
- UI Skills: focused UI quality and accessibility guidance
- Strix: operational/live-data state handling
- Supabase: dashboard/product UI primitives and shell patterns
- Playwright CLI: real-browser validation and evidence collection

## Useful capabilities

### Visual QA
- screenshot captures the actual rendered page or a specific element.
- resize tests the same interface at controlled viewport dimensions.
- open --mobile and open --device support mobile/device-oriented checks.
- show --annotate provides a visual session view for UI review and design feedback.
- highlight can make the exact element under review visually explicit.

### Structural and interaction inspection
- snapshot captures page or element structure with interaction refs.
- find searches a large snapshot without loading the entire page into the workflow.
- CSS selectors, role locators, and test IDs support targeted interaction.
- generate-locator can turn an inspected element into a Playwright locator.
- eval and run-code allow targeted browser inspection when the normal CLI surface is insufficient.

### Runtime evidence
- console exposes browser console messages.
- requests and request expose network activity.
- tracing-start/stop records execution traces for difficult interaction/runtime bugs.
- recording-start/stop can turn manual browser actions into Playwright code.
- video-start/stop captures a visual reproduction when a static screenshot is not enough.

### Stateful browser checks
- Sessions keep browser state across commands.
- state-save/state-load support reproducible authenticated or stateful flows.
- Persistent profiles can preserve browser state between restarts.
- Named sessions allow separate browser contexts for separate projects or scenarios.

## Standard use in UI work

Use Playwright CLI when a real browser is available and the task needs evidence from the rendered implementation:

1. Open the real page.
2. Capture a baseline screenshot at the reference viewport.
3. Capture a snapshot when structure or interaction needs inspection.
4. Exercise the relevant interaction path.
5. Capture the resulting state.
6. Resize to relevant desktop/tablet/mobile viewports and repeat.
7. Check console/network output when behavior is unexpected.
8. Use trace/video only when the failure is difficult to reproduce from screenshots.
9. Compare captures against guidelines/visual-comparison.md.
10. Record the concrete difference, fix the implementation, then recapture.

## Important constraints

- Playwright CLI is a validation/execution layer, not a replacement for visual judgment.
- A successful browser action does not prove that the UI is visually correct.
- Snapshots describe page structure and interaction targets; they do not replace screenshots for visual comparison.
- Console/network/trace evidence should diagnose implementation problems, not invent visual conclusions.
- Do not copy Playwright CLI source or its CLI/Node architecture into WordPress. Use the workflow principles and browser capabilities.
- Do not assume a single viewport proves responsive correctness.
- Treat browser state, authentication, cookies, and storage as project-specific and avoid committing secrets or private state.

## Best fit

Especially useful for:
- screenshot-to-WordPress implementation QA
- responsive visual comparison
- interactive menus, forms, modals, tabs, filters, and dashboards
- reproducing UI bugs
- collecting before/after evidence
- validating loading/empty/error/live states in the browser
- checking console/network failures behind a visual symptom
