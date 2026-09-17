# Review Output and Test Matrix

Read this reference when the user asks for a formal UX review, prioritized findings, a validation plan, or broader coverage than one requested interaction.

## Scale validation to risk

Choose the smallest tier that covers the task. Move upward when persistence, external effects, irreversibility, ambiguity, or affected users increase risk.

| Tier | Typical task | Minimum useful coverage |
| --- | --- | --- |
| A: Read or navigate | Find information, open a detail page, compare content | Initial orientation, primary path, semantic destination, Back/context preservation when relevant |
| B: Reversible local change | Search, filter, sort, select, configure, edit an unsaved draft | Tier A plus one wrong choice or empty state, reset/correction, state visibility, keyboard path |
| C: Persistent or asynchronous work | Saved edits, dashboards, canvases, uploads, AI generation, queued jobs | Tier B plus interruption/failure, undo or stop, partial-result meaning, reload/reopen, persistence and recovery horizon |
| D: External commitment | Send, publish, pay, authorize, delete, change permissions | Tier C plus object/scope/account review, consequence-specific action label, authorization boundary, destination verification, durable receipt or compensation |

This matrix selects coverage; it does not grant permission to cross a commitment boundary. Stop before an unauthorized external effect.

Add narrow or touch testing only when responsive behavior matters. Add domain verification when the interface's meaning depends on facts that visual or structural evidence cannot prove.

## Keep four state ledgers separate

For each tested path, record only the ledgers that can change the outcome:

| Ledger | Examples | Evidence |
| --- | --- | --- |
| Context | account, role, workspace, locale, time range, data source, filter | visible label, selected state, URL, object identity, data scope |
| Interaction | mode, selection, focus, viewpoint, history, persistence | control state, object state, focus target, undo/redo, reload/reopen result |
| Execution | accepted, queued, running, streaming, paused, failed, complete | status text, progress, partial output, terminal state, destination state |
| Authority | provisional, inspectable, verified, committed | source, review, calculation, confirmation, durable external record |

Do not infer one ledger from another. Saved content does not prove undo history survived; a completed job does not prove its result is correct; a changed URL does not prove the intended object was reached.

## Separate evidence, judgment, priority, and boundary

These answer different questions and must not be collapsed into one label.

### Evidence basis: what supports the statement?

- **Direct observation:** a rendered state, interaction, focus target, object change, destination, or failure was actually observed.
- **Source or standard evidence:** implementation, documentation, specification, or an authoritative external record supports the statement.
- **Reasoned inference:** observed behavior plus established interaction logic suggests an impact that was not directly measured.
- **User or field evidence:** research, analytics, support data, or repeated real-world behavior demonstrates the impact.

Name unobserved assumptions under the boundary instead of presenting them as evidence.

### Finding class: what kind of judgment is being made?

- **Failure:** the tested task breaks, information or operation is inaccessible, state is wrong, input is lost, or a standard is violated.
- **Strong usability concern:** the path works, but evidence indicates likely error, hesitation, exclusion, or excess effort.
- **Design hypothesis:** the proposed improvement depends on audience, frequency, content, business rules, or comparative user research.
- **Positive finding:** observed behavior correctly supports the task and should be preserved.

A directly observed fact can still support a hypothesis rather than a failure. For example, initial focus on an explanatory link is observable; whether that placement harms a particular workflow may require user evidence.

### Priority: what should change first?

Assign priority only after describing evidence and impact:

| Priority | Meaning |
| --- | --- |
| P0 | Unsafe or blocks the primary task for the intended user; no practical recovery |
| P1 | High-likelihood or high-consequence failure in an important path |
| P2 | Meaningful friction, ambiguity, or exclusion with a workaround |
| P3 | Limited polish or efficiency improvement |

Do not create numerical usability scores from these labels. A hypothesis can be important, but should not be presented as a P0 defect without supporting impact evidence. Do not lower priority merely because the affected users are a minority; consider task blockage, consequence, frequency for those users, recovery, and product obligations.

### Boundary: what is not known?

Record untested devices, assistive technologies, accounts, data states, real consequences, domain meaning, and audience assumptions. A missing product capability or an intentionally unsupported demo behavior is a boundary until evidence shows that the intended task requires it.

## Report the decision path

For each finding, include:

1. **Finding:** one concrete problem, named from the user's perspective.
2. **Path:** the shortest reproduction sequence and relevant state.
3. **Evidence:** what was observed and through which representation.
4. **Impact:** which user or task is affected and how.
5. **Smallest appropriate improvement:** fix the broken decision or recovery point without redesigning unrelated parts.
6. **Evidence basis:** direct observation, source/standard, inference, or user/field evidence.
7. **Finding class and priority:** failure, concern, hypothesis, or positive finding; then P0–P3 when action is warranted.
8. **Boundary:** what remains untested or requires domain/user evidence.

Also record important behavior that worked. This prevents a successful mechanism from being erased by one concern and prevents a successful happy path from hiding semantic or recovery failures.

## Use a concise review structure

Prefer this order:

1. Outcome and scope.
2. Interaction contract: result, context, assumptions, commitment boundary, evidence, stop condition.
3. Tested paths and states.
4. Prioritized findings.
5. What worked.
6. Untested boundaries and design hypotheses.

Do not turn the report into a component inventory. Group repeated symptoms under the earliest broken point in the user's interaction loop.

## Stop deliberately

Stop when the selected tier has enough evidence to support the requested judgment and no visible state contradicts it.

- Do not collect redundant screenshots or repeat a successful action.
- Do not retry a no-progress action more than twice without a new diagnosis.
- Do not cross an external commitment boundary merely to make a review feel complete.
- Do not generalize a product-specific example into a new skill rule unless it changes decisions across multiple plausible interfaces.
