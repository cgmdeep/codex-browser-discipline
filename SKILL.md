---
name: codex-browser-discipline
description: Improve Codex Browser and Computer Use decisions for interactive website operation and evidence-backed UX review by defining semantic success, evaluating ergonomic layout and intuitive transitions, preserving context, managing commitment boundaries, and recovering without wandering. Use when Codex operates a website, reviews interaction design, or validates a rendered web UI. Do not use for search-only research, HTTP/API-only work, or code-only frontend implementation without live interaction.
---

# Codex Browser Discipline

Use the selected Browser or Computer Use API exactly as its current documentation describes. This skill changes the interaction strategy; it does not replace the runtime, relax confirmation requirements, or authorize actions beyond the user's request.

## Route only to relevant detail

- For ordinary website operation, use the core loop in this file and verify only the requested outcome.
- For an unfamiliar, hybrid, or newly named interface, first read [references/cognitive-task-model.md](references/cognitive-task-model.md) and decompose the page by the user's cognitive work instead of inventing a new page-type checklist.
- For layout, ergonomics, usability, information architecture, navigation review, or rendered frontend validation, read [references/ux-interaction-review.md](references/ux-interaction-review.md).
- For forms, multi-step flows, checkout, permissions, publishing, deletion, payment, or other consequential submissions, also read [references/forms-and-commitment.md](references/forms-and-commitment.md).
- For dashboards, tables, maps, canvases, editors, or direct manipulation, also read [references/data-and-direct-manipulation.md](references/data-and-direct-manipulation.md).
- For streaming AI, long-running automation, agents, generated results, or external tool actions, also read [references/async-ai-and-automation.md](references/async-ai-and-automation.md).
- For a formal UX review, prioritized findings, or a reusable validation plan, read [references/review-output-and-test-matrix.md](references/review-output-and-test-matrix.md) after the relevant scenario reference.

Do not load unrelated references merely because a page contains one incidental component.

## Decompose unfamiliar interfaces by user work

Do not assume that a product label such as CRM, portal, cockpit, knowledge base, editor, or AI workspace determines its interaction requirements. Identify the small set of cognitive tasks the user must complete, combine only their relevant checks, and scale coverage by consequence. Locate the earliest broken transition in that task sequence rather than producing a component inventory.

## Establish the interaction contract

Before the first page-changing action, derive:

1. The user's concrete outcome and what it means semantically, not just which control to click.
2. The intended tab, site, account, workspace, object, and scope when visible.
3. Any assumption likely to change the result, such as location, time range, filters, locale, permissions, data source, or selected item.
4. The cheapest evidence strong enough to prove the requested outcome.
5. Whether the next action browses, drafts, executes reversibly, or crosses a commitment boundary with external consequences.
6. The condition for stopping.

Do not silently broaden the goal from reading or diagnosis into an external mutation.

## Verify the right level of success

Treat success evidence as a hierarchy:

```text
action accepted
  -> interface changed
  -> system state changed
  -> result meaning matches the intent
  -> the user's task is complete
```

The first three levels prove mechanism, not necessarily success. A changed URL, moved map, toast, selected state, or generated answer can still contradict the user's intended object or meaning. Seek semantic or task evidence when the claim requires it. If domain meaning cannot be verified, label that limitation instead of substituting visual change.

## Choose page evidence deliberately

Use the least expensive representation that can answer the next decision:

1. Fresh accessibility state for ordinary reading, targeting, focus, and interaction state.
2. A fresh full accessibility state when a diff lacks necessary context.
3. A screenshot when layout, geometry, images, canvas, occlusion, density, or visual feedback matters.
4. Scoped semantic locators or DOM inspection for repetitive work or when accessibility cannot express the target.
5. Coordinates only when no usable semantic target exists and a current screenshot makes the target unambiguous.
6. Raw page evaluation only for capabilities unavailable through higher-level APIs.

Do not request accessibility state and a screenshot together by default. Do not descend this ladder merely because one action failed; inspect the resulting state first.

## Observe, act, verify

Repeat until the contract's stopping condition is satisfied:

1. Observe enough current state to identify the target by role, accessible name, state, and surrounding task context.
2. Predict the expected direct change and any important consequence.
3. Act on the fresh target.
4. Wait for an observable condition rather than an arbitrary delay when possible.
5. Collect the cheapest evidence needed for the next decision.
6. Re-evaluate the result against the original semantic outcome and current system assumptions.

Batch actions only while page structure and consequence remain stable, such as filling independent fields. Stop and re-observe before navigation, submission, dialogs, tab changes, or external side effects.

Never reuse accessibility indices, element references, or assumptions after navigation or a meaningful DOM change.

## Require adequate target confidence

Prefer a unique semantic target whose role, accessible name, state, nearby section, and current object match the user's intent. Do not choose an element merely because it appears first or has a vaguely similar label.

When multiple plausible targets remain:

- Narrow observation to the relevant region or inspect geometry.
- Reveal menus, expanders, or obscured controls before targeting their children.
- Check the active account, workspace, object, filter, location, or time range when acting on the wrong one would matter.
- Ask the user only when visible evidence cannot resolve a choice that materially changes the result.

## Match control and recovery to consequences

Distinguish recovery mechanisms instead of treating them as synonyms:

- **Correct:** repair input before commitment while preserving valid work.
- **Undo:** restore a previous state after a reversible change.
- **Retry:** execute the same failed step again under the same intended conditions.
- **Compensate:** reduce an irreversible consequence through cancellation, refund, appeal, or human support.

Use review or confirmation at the commitment boundary when consequences justify it. Prefer reversible actions over repetitive confirmation friction. Never infer that approval for one step authorizes a different external effect.

## Recover from interaction failures without wandering

For an action with no clear effect:

1. Inspect current state for an overlay, dialog, loading state, validation error, focus problem, stale target, unexpected navigation, or contradicted assumption.
2. Retarget the same intended action using fresh evidence and the most direct semantic method.
3. Retry once only when the new evidence supports it.

Do not repeat the same action more than twice without a materially different diagnosis. After two no-progress attempts, use an available handoff mechanism or report the concrete blocker.

Focused recovery examples:

- Stale target: refresh accessibility state and resolve it again.
- Covered click: handle the visible blocker if it is within scope.
- Missing control: check loading, relevant scrolling, selection, or a collapsed region; do not explore unrelated areas.
- Input mismatch: inspect the displayed value, then use the documented alternative once.
- Transitional state: wait for the expected visible condition.
- Login, CAPTCHA, OTP, payment, permission, destructive consequence, or unresolved account choice: apply the existing authorization or human-handoff policy.

## Stop at the requested outcome

Stop when adequate evidence supports the semantic outcome and no visible signal contradicts it. Do not refresh, navigate elsewhere, repeat the action, or collect redundant confirmations merely to feel more certain.

Close only task-owned temporary tabs or sessions when cleanup is appropriate. Preserve user-owned tabs and in-progress state unless asked to change them.

For UX reviews, separate the evidence basis, finding class, priority, and untested boundary. Treat ergonomic and intuitive-design conclusions as evidence-backed judgments, not universal facts.
