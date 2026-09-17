# UX Interaction Review

Read this reference when the task asks whether a rendered web page is ergonomic, intuitive, easy to navigate, or logically organized, or asks to improve those qualities.

## Frame the review

Identify the primary user, likely device and input method, entry point, and main task. If these are not explicit, infer a reasonable default from the product and state the assumption. Review the page around that task instead of grading every possible design preference.

Define the target journey as:

`entry context -> user decision -> control -> transition -> feedback -> semantic verification -> next sensible action`

Use screenshots for spatial and visual judgments, accessibility state for structure and operability, and real clicks or keyboard input for behavioral claims. Inspect the initial viewport before scrolling.

If the journey contains consequential submission, direct manipulation, or asynchronous AI, read the matching reference routed from `SKILL.md`; do not force those state models onto an unrelated page.

## Evaluate layout ergonomics

Check whether the layout reduces searching, pointer travel, accidental activation, memory load, and repeated backtracking:

- The page has a clear visual hierarchy and one obvious starting point for the primary task.
- Related content and controls are grouped spatially; controls appear near the content they affect.
- Primary actions are easy to find without competing with secondary or destructive actions.
- Repeated structures use consistent alignment, spacing, labels, placement, and control behavior.
- Text density, line length, whitespace, and section width support scanning and sustained reading.
- Sticky headers, floating controls, banners, dialogs, and tooltips do not cover required content or focus.
- Required content and controls are not clipped or forced into unnecessary two-dimensional scrolling.
- Responsive layouts preserve task order and hierarchy rather than merely shrinking the desktop layout.
- Pointer targets are at least 24 by 24 CSS pixels or have sufficient separation under WCAG 2.2. Prefer approximately 44 by 44 CSS pixels for important touch targets when the design allows it.
- Dense toolbars and adjacent destructive controls provide enough size and separation to limit misclicks.

Do not judge ergonomics only from element dimensions. A large target can still be hard to discover, ambiguously labeled, visually detached from its effect, or placed far from the user's current focus.

## Evaluate affordance and interaction logic

Each interactive element should communicate what it is, whether it is available, and what will happen:

- Links navigate; buttons perform actions. Use conventional roles and appearances unless a different pattern has a clear product reason.
- Labels and icons predict the result in the user's language. Icon-only controls have an accessible name and a familiar or explained symbol.
- Interactive elements expose visible hover, focus, pressed, selected, disabled, loading, success, and error states when those states apply.
- Disabled actions explain the unmet condition when it is not obvious.
- The primary action is visually prominent; destructive actions are separated and clearly identified.
- Controls do not trigger surprising navigation merely on focus, hover, field entry, or selection.
- The interface shows progress or status promptly after an action and places validation or error feedback near the affected control.
- Forms preserve valid user input after errors and move focus or attention to a useful recovery point.
- Keyboard focus order preserves the visual and task sequence, and the focus indicator remains visible.
- The design does not rely only on color, hover, precision pointing, or hidden gestures for essential meaning or operation.

Use tooltip, hover card, or popover for supplementary explanation when it reduces clutter. Essential instructions, risk, current state, and recovery actions must remain available without hover; hover-revealed content should also be reachable by keyboard focus and have a workable touch alternative.

When a pattern departs from common platform or web conventions, ask whether the gain is large enough to justify the learning cost.

## Validate click and navigation behavior

Test navigation as a human expectation, not merely as a successful click:

1. Before clicking, infer the expected destination or state change from the control's label, role, surrounding copy, and current context.
2. Activate the real rendered control using the intended input method.
3. Verify that the destination URL, page title or heading, breadcrumb, selected navigation state, and rendered content agree with the expectation.
4. Check that important context survives the transition when users would expect it, such as filters, scroll position, form state, or the selected item.
5. Check that the destination object and meaning satisfy the user's intent; navigation can be mechanically successful and semantically wrong.
6. Verify that the next useful action is apparent and that the user is not left at a dead end.

Also check when relevant:

- Back navigation returns to a sensible prior state without losing avoidable work.
- Internal links stay in the same tab unless a parallel context is genuinely useful; unexpected new tabs are defects.
- External destinations, downloads, and context changes are signaled before activation when surprise would matter.
- Navigation items have consistent destinations and selected states across pages.
- Logo, breadcrumbs, tabs, side navigation, and browser Back do not provide contradictory routes.
- Redirects, loading states, empty states, permission gates, and errors explain what happened and how to continue.
- Repeated clicks during loading do not duplicate submissions or create conflicting state.

## Test representative human paths

Scale coverage to the request. For a focused review, test:

- One primary happy path from entry to completion.
- One plausible hesitation, wrong choice, empty input, or recoverable error.
- Keyboard-only operation through the relevant controls.
- The intended desktop viewport and one realistic narrow or touch viewport when responsive behavior matters.

For each meaningful transition, capture the cheapest proof of the state before and after. Use screenshots at states where spatial relationships, visual hierarchy, or feedback are part of the claim.

Do not substitute scripted DOM mutation for user input when judging whether an interaction is understandable and operable.

For forms and multi-step flows, use [forms-and-commitment.md](forms-and-commitment.md) instead of duplicating their validation, review, commitment, and completion rules here.

## Classify findings honestly

Label findings by evidence type:

- **Failure:** observable breakage, inaccessible operation, wrong destination, hidden required content, lost input, or a standards violation.
- **Strong usability concern:** a clear convention mismatch or interaction likely to cause errors, hesitation, or excess effort.
- **Design hypothesis:** a plausible improvement whose benefit depends on audience, frequency, content, or product goals and should be tested with users or analytics.

Prioritize by task blockage, error likelihood, frequency, effort, recoverability, and affected users. Explain the visible problem, reproduction path, evidence, and smallest appropriate improvement. Do not present personal taste as ergonomics.

## Standards basis

Use these as baselines rather than a substitute for product context:

- WCAG 2.2 target size minimum: https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html
- WCAG 2.2 enhanced target size: https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html
- WCAG focus order: https://www.w3.org/WAI/WCAG22/Understanding/focus-order.html
- WCAG reflow: https://www.w3.org/WAI/WCAG22/Understanding/reflow.html
- WCAG status messages: https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html
- Nielsen Norman Group usability heuristics: https://www.nngroup.com/articles/ten-usability-heuristics/
- GOV.UK button guidance: https://design-system.service.gov.uk/components/button/
- GOV.UK error-message guidance: https://design-system.service.gov.uk/components/error-message/
