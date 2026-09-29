# Browser QA with Playwright

## When to use it

Use Playwright CLI for real-browser validation when the rendered result, interaction behavior, or runtime state needs evidence.

## Validation loop

1. Open the real implementation.
2. Set the reference viewport.
3. Capture a screenshot.
4. Capture a snapshot when DOM structure or interaction targets matter.
5. Exercise the target interaction.
6. Capture the resulting state.
7. Repeat at relevant responsive viewports.
8. Inspect console/network output when behavior is unexpected.
9. Use trace/video for hard-to-reproduce failures.
10. Compare against the reference and fix the implementation.

## Evidence hierarchy

Use the least expensive evidence that answers the question:
- screenshot for visual differences
- snapshot for structure and interaction targets
- console/network for runtime symptoms
- trace/video for complex timing or interaction failures

Do not treat one evidence type as proof of another. A clean console does not prove visual fidelity; a successful click does not prove correct interaction design.

## Responsive checks

At minimum, validate the viewports required by the project. Do not assume desktop correctness implies mobile correctness.

Check:
- header/navigation
- grids and cards
- typography and wrapping
- buttons and controls
- overflow and clipping
- fixed/sticky elements
- modal/dropdown behavior
- touch-oriented interaction where applicable

## Stateful and asynchronous UI

For dashboards and dynamic interfaces, deliberately test:
- loading
- live/in-progress
- completed
- empty
- unavailable
- partial
- error
- dataset or filter changes

Confirm that visible counts, lists, filters, selected state, and detail views still describe the same dataset after asynchronous updates.

## Reproduction discipline

For a bug:
- start from a clean or explicitly documented browser state
- record the exact viewport and interaction path
- capture the failing state
- inspect console/network only after confirming the visible symptom
- use trace/video if timing or multi-step interaction matters
- fix the smallest relevant implementation area
- rerun the same path and capture the corrected state

Never commit authentication tokens, cookies, storage state, or other private browser artifacts.
