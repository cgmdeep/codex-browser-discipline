# Cognitive Task Model

Read this reference when the interface is unfamiliar, combines several product patterns, or has a name not covered by another scenario reference. It prevents page labels and component catalogs from becoming the review model.

## Select the user's actual cognitive tasks

Most interactive pages combine a small subset of these task families:

1. **Orient:** know the current place, object, account, scope, and entry point.
2. **Interpret:** understand a term, metric, status, source, or confidence level.
3. **Compare and decide:** align alternatives, units, baselines, tradeoffs, and uncertainty.
4. **Filter and focus:** know which subset is visible, why it changed, and how to reset it.
5. **Enter and correct:** express intent, see constraints, preserve valid input, and recover from errors.
6. **Directly manipulate:** select, move, edit, resize, or transform the intended object while keeping state and history visible.
7. **Drill down and return:** inspect detail while preserving the parent scope, selection, position, and useful way back.
8. **Wait and supervise:** distinguish queued, running, paused, failed, stopped, and complete states and know when intervention is possible.
9. **Commit:** verify the object, account, scope, audience, consequence, reversibility, and durable receipt before an external effect.
10. **Recover:** correct, undo, retry, compensate, or resume without losing valid work or disguising partial results as success.

Select only the families present in the user's intended journey. A search page may require orient, enter and correct, compare, drill down, and return; it does not automatically require every rule associated with forms or dashboards.

## Add only relevant cross-cutting conditions

For each selected family, ask which conditions can change the outcome:

- **Input:** pointer, keyboard, touch, voice, or assistive technology.
- **Space:** wide or narrow viewport, zoom, scrolling, occlusion, and dense controls.
- **Data:** empty, one result, many results, exceptional values, latency, stale data, or insufficient permission.
- **Time:** loading, streaming, background execution, refresh, reopen, and cross-session persistence.
- **Consequence:** read-only, reversible local change, persistent asynchronous work, or external commitment.

Use `selected cognitive tasks × relevant conditions × consequence tier` as the coverage model. Do not multiply every family by every condition when the task does not justify it.

## Build and test the journey

Write the journey as:

`entry context -> user decision -> control -> transition -> feedback -> semantic result -> next sensible action`

Then:

1. Name the expected meaning of each transition before activating it.
2. Check context, interaction, execution, and authority ledgers only where they can change the result.
3. Include one realistic correction or recovery path for reversible interactive work.
4. Verify return behavior when the user may need to compare, revise, or continue from a parent view.
5. Report the earliest broken cognitive task, its evidence, impact, and boundary; do not list every weak component separately.

Repeated symptoms across different product labels may support a general skill rule. A one-off visual preference or product-specific capability gap stays in the review report until broader evidence changes Codex's decisions.
