# Strix

Official project: https://github.com/usestrix/strix

Strix is an open-source AI penetration-testing platform. It is **not** a UI dependency for this repository. We use its local web viewer and agent-oriented workflow as a reference for operational dashboards, evidence-driven findings, and stateful report interfaces.

## What we adopt

### 1. Findings are evidence objects, not decorative cards

Strix models findings with structured severity and detailed evidence, then exposes a finding list and a dedicated detail view.

For analytical or operational UI:
- keep the headline finding separate from its evidence
- show severity/status consistently
- make the detail path easy to reach
- do not imply certainty beyond the available evidence
- keep counts synchronized with the underlying records

A visual badge or count must correspond to the same dataset the detail view uses.

### 2. Explicit runtime states

The viewer distinguishes live runs, finished runs, loading, errors, empty history, and unavailable data.

For data-heavy UI, explicitly design the relevant states:
- loading
- live/in progress
- completed
- empty
- unavailable / not yet available
- error
- partial data when only some sources have completed

Do not make a blank area carry the meaning of a state.

### 3. Preserve user navigation during live updates

Strix polls a live run but does not continuously override a user's manually selected view. Initial automatic navigation is applied only when appropriate; explicit user navigation wins.

For live dashboards:
- update data without unexpectedly changing the user's current section
- apply automatic default navigation only once per relevant state/run
- reset state when switching to a different dataset
- stop polling when the data source is finished
- cancel/ignore stale asynchronous responses after the active dataset changes

### 4. Separate summary from detail

A useful operational report can have:
- summary/overview
- grouped findings
- detailed finding view
- historical runs or snapshots
- runtime/configuration details

Do not force every detail into the overview. Use progressive disclosure for secondary information.

### 5. Consistent severity and status vocabulary

If severity/status is used, define a small vocabulary and reuse it across:
- summary counts
- lists
- badges/dots
- detail views
- historical views
- filters

The same finding should not appear with contradictory labels or counts on different surfaces.

### 6. Operational history

Historical runs are more useful when each entry exposes compact context such as:
- name/target
- time
- status
- severity summary
- active/current state

Use relative time for recent activity when helpful, with an absolute date as a fallback for older records.

### 7. Trust and data provenance

Strix makes the data boundary explicit in its local viewer.

For UI that handles sensitive, external, or user-generated data:
- state where the data comes from when it matters
- distinguish local, remote, cached, and live data when relevant
- avoid implying that a value was verified if the source was unavailable
- make important limitations visible near the affected result

### 8. Small, purposeful motion

Strix uses short transitions and state animation, but its implementation also demonstrates why motion needs a performance budget.

For this repository:
- use motion to communicate state or hierarchy
- prefer transform/opacity for transitions
- keep list/card entrances short and restrained
- avoid animating large DOM trees unnecessarily
- provide reduced-motion behavior

## What we do not copy

Do not copy Strix's pentesting logic, security tooling, cloud integrations, or React/Tailwind implementation into this repository.

This reference extracts UI and dashboard patterns only.

## Relationship to existing standards

- Screenshot-to-Code → visual prototype generation
- Context7 → current library/API verification
- UI Skills → baseline UI quality, accessibility, motion, design-system evidence
- Strix → operational dashboard states, evidence-oriented findings, live-update behavior, history, and provenance
