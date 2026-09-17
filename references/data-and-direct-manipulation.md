# Data and Direct Manipulation

Read this reference for dashboards, tables, monitoring surfaces, charts, maps, canvases, editors, diagrams, or other interfaces whose meaning depends on dense data or continuous interaction state.

## Evaluate data as a decision surface

Separate three levels:

1. **Display:** the value, chart, table, or object is visible.
2. **Interpretation:** labels, units, time range, source, freshness, aggregation, comparison, and uncertainty make its meaning understandable.
3. **Decision:** thresholds, anomalies, consequences, drill-down, or appropriate next actions help the intended user decide what to do.

Do not automatically simplify a dense expert interface. Judge density against user expertise, task frequency, scanning pattern, screen size, and consequence. Preserve expert efficiency while making important context inspectable.

For filters, legends, metric cards, maps, and search results, verify the actual semantic object and scope. A chart update or map movement proves state change, not that the selected data, place, time, or unit matches the user's intent.

When filtering, sorting, grouping, pagination, collapsing, or virtualization can remove data from the current view, keep the active transformation and the visible-versus-total scope perceivable. Distinguish “not in this view” from “not in the data,” provide a clear way to reset the transformation, and do not convey the state through color or a small icon alone.

For data grids, verify that row and column headers remain programmatically associated with their values, that sort and filter state is announced semantically, and that the same operations are available without precision pointing. Spatial alignment alone is not an adequate substitute for table semantics.

## Track continuous state

Page title and URL are insufficient for direct manipulation. Observe:

| State | Question |
| --- | --- |
| Mode | Which tool or interaction rule is active? |
| Selection | Which object will the next action affect? |
| Viewpoint | What location, zoom, layer, range, or viewport is being shown? |
| History | What can be undone, redone, compared, or restored? |
| Persistence | Where is the work saved, for how long, and has it synchronized? |

Verify manipulation through the object or canvas state itself, plus history or persistence when relevant. Do not rely on a click event or highlighted toolbar button alone.

Treat these states as related but independent. A reload can preserve content while clearing undo history; it can restore a selection while changing focus, mode, viewport, or synchronization status. When continuity matters, verify the saved content, current interaction context, and recovery horizon separately.

For canvas-style interfaces, verify that a non-visual user can identify relevant objects, their content, the current selection, and the target of the next action. A keyboard shortcut is not an equivalent path when the object can only be found or selected through precision pointing.

## Preserve mode visibility and safe exploration

- Make the active tool, selection, scope, and constraints perceivable near the work.
- Distinguish selection from transformation: selecting a column, changing its sort order, and filtering its values need different, persistent feedback.
- Provide immediate object-level feedback for creation, movement, resizing, filtering, zooming, and deletion.
- Keep undo and redo semantics predictable; show when they are unavailable.
- Make the recovery horizon legible when it changes, especially after reload, reopen, synchronization, import, or mode changes.
- Avoid hidden destructive gestures or precision-only paths.
- Surface storage, synchronization, or unsaved-work risk before it can cause loss.

## Use progressive disclosure without hiding essentials

Tooltips and popovers can explain unfamiliar terms, abbreviations, metric definitions, calculations, or secondary controls. Do not place the only copy of a unit, current mode, material risk, or required action behind hover. Ensure focus and touch alternatives, keep the trigger associated with what it explains, and avoid covering the data or control under discussion.

When a dashboard needs substantial explanation, prefer a stable definition panel, glossary, drill-down, or contextual details view over many fragile tooltips.
