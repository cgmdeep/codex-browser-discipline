# Forms and Commitment Boundaries

Read this reference for multi-step forms, checkout, applications, permissions, publishing, deletion, payment, or other actions whose consequences make correction important.

## Find the commitment boundary

Separate browsing, drafting, reversible execution, and commitment. Identify the first action that creates a legal, financial, permission, communication, publication, deletion, or other difficult-to-recover consequence.

Place protection around that boundary:

| Stage | Useful protection |
| --- | --- |
| Before commitment | Explain consequences, validate input, review, and allow local changes |
| At commitment | Identify the object, scope, action, account, and permission being used |
| After a reversible change | Undo, cancel, restore, or version history |
| After an irreversible change | Compensation, refund, appeal, support, and a durable receipt |

Do not equate protection with an extra confirmation dialog. Frequent low-consequence confirmation trains mechanical acceptance. Prefer clear labels, review, and reversibility; add confirmation when the consequence and timing justify its interruption cost.

## Make validation a recovery path

On validation failure:

1. Preserve all valid input and task context.
2. State what is wrong in text, not by color alone.
3. When the correction is known, say how to correct it.
4. Put local guidance near the affected field.
5. For multiple or distant errors, provide a global summary whose items move focus to the relevant control.
6. Move initial attention to a useful recovery point without trapping focus.
7. After correction, return the user to the appropriate next step rather than forcing unnecessary repetition.

Global and local error messages are complementary when one supports overview and the other supports correction. Keep their wording semantically consistent.

Distinguish invalid user input from service failure, ineligibility, or missing permission. Do not ask the user to “fix” a condition outside their control; explain the condition and a realistic next action.

## Support review and correction

Before consequential submission, make the review answer:

- What will happen?
- To which object, person, account, or audience?
- Which values and scope are being used?
- Which dependent surfaces or objects will also change, such as published pages, URLs, forks, integrations, automations, credentials, collaborators, or downstream audiences?
- Can the user change one answer without replaying the whole flow?
- What remains reversible afterward?

Do not treat an interface's consequence list as complete merely because it appears in a confirmation dialog. When the current object visibly has a relevant dependency that the review omits, verify the effect from an authoritative source when proportionate to the risk, or label it unknown and stop before commitment.

Use action-specific labels such as “Send application,” “Publish to everyone,” or “Delete 3 files” when the added specificity matters. Repeated generic links such as “Change” need object-specific accessible names.

Keep one visually dominant primary action near the reading end of each step. Secondary, corrective, and destructive actions should not compete with it or appear detached from the content they affect.

## Prove completion persistently

After commitment, prefer a durable state containing the outcome, identifying details or reference number, time when relevant, next steps, and recovery or contact path. A transient toast can supplement this evidence but should not be the only receipt for an important transaction.

## Standards basis

- WCAG 2.2 error identification and suggestion: https://www.w3.org/TR/WCAG22/#input-assistance
- WCAG 2.2 error prevention for legal, financial, and data actions: https://www.w3.org/TR/WCAG22/#error-prevention-legal-financial-data
- GOV.UK error summary: https://design-system.service.gov.uk/components/error-summary/
- GOV.UK check answers: https://design-system.service.gov.uk/patterns/check-answers/
- GOV.UK confirmation pages: https://design-system.service.gov.uk/patterns/confirmation-pages/
