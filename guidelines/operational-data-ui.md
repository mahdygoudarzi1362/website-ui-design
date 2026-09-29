# Operational Data UI Guidelines

Use this guideline for dashboards, analytics reports, monitoring screens, audit views, and other interfaces where data changes over time or findings need evidence.

## 1. Model the state before styling it

Identify which states the component can actually enter:

- loading
- live / processing
- completed
- empty
- unavailable
- error
- partial

Give each state an explicit UI treatment and, where useful, a next action.

Do not use a spinner for a state that actually means "no data" or "not available".

## 2. Keep summary counts and detail records in sync

For every headline count, define its source dataset.

Examples:
- total findings = records shown by the corresponding finding list
- severity count = records matching that severity
- history count = runs represented by the history view

If a card says "45 items" while its modal contains 17 unrelated records, the UI is misleading even if both numbers are individually valid.

## 3. Evidence-first finding design

A finding should answer, at the appropriate level:

1. What was detected?
2. What is the status/severity?
3. What evidence supports it?
4. What action or detail is available next?

Do not bury evidence behind unnecessary navigation when the evidence is essential to interpreting the result.

## 4. Live data must not fight the user

When polling or streaming:
- keep the user's current view stable
- do not repeatedly reset tabs, filters, or selected records
- apply automatic initial navigation only once
- cancel or ignore stale requests after the active dataset changes
- stop polling when the source reaches a terminal state
- distinguish live values from finalized values when the distinction matters

## 5. Progressive disclosure

Use layers:
- overview for orientation
- grouped list for scanning
- detail view for investigation
- configuration/history for secondary context

Avoid putting every diagnostic field into the first screen.

## 6. Status and severity vocabulary

Define status/severity values once and reuse them consistently.

The same semantic state should not receive different colors, labels, or meanings across cards, tables, modals, and charts.

Color must not be the only carrier of status.

## 7. History and comparison

Historical entries should expose enough compact context to identify the record without opening it.

Where relevant include:
- target/name
- timestamp
- status
- compact severity or outcome summary
- active/current indicator

For recent records, relative time can improve scanning; older records should fall back to an unambiguous date.

## 8. Provenance and limitations

When a value comes from an external or optional source:
- identify the source when it affects interpretation
- distinguish detected, not detected, unavailable, and not comparable where appropriate
- explain meaningful coverage limitations
- never convert missing evidence into a positive or negative finding

This is especially important for analytics, SEO, monitoring, and technical reports.

## 9. Runtime resilience

Async UI should tolerate:
- slow first load
- partial responses
- temporary failures
- dataset switching
- stale responses
- empty results

A failed secondary source should not necessarily destroy a usable primary report.

## 10. Final QA

Before approval, test at least:
- loading
- empty
- error
- live/in-progress
- completed
- one populated finding
- many findings
- zero findings
- dataset/history switching
- mobile/dense layouts

Check that counts, labels, filters, details, and visible records all describe the same underlying state.
