# Async AI and Automation

Read this reference for streaming generation, queued jobs, agents, long-running automation, probabilistic results, or interfaces where an AI can call tools and affect external systems.

## Separate execution from result authority

Track two axes independently:

```text
Execution: idle -> accepted -> queued -> running/streaming -> paused/failed/completed
Authority: provisional -> inspectable -> verified -> committed
```

Completion of execution does not prove correctness. Streaming or partial output may be useful, but label it as incomplete and do not present it with the authority of a verified result.

Show enough status for the user to know:

- what is running and for which input or object;
- whether it is waiting, using a tool, blocked on user input, or complete;
- what can still be changed or stopped;
- which external effects have already happened;
- how the user can inspect the final result.

Do not expose internal implementation detail merely to look transparent. Show information that changes the user's understanding, control, trust, or next action.

## Name recovery actions by their real semantics

Do not treat these as synonyms:

| Action | Required meaning |
| --- | --- |
| Pause | Preserve enough execution context to continue from the same progress |
| Stop or cancel | End the current execution and disclose retained output and completed side effects |
| Continue | Proceed with the existing task and context |
| Retry | Execute the same failed step under the intended same conditions |
| Regenerate | Produce a potentially different result and disclose replacement, version, or downstream-history effects |
| Edit or branch | Clarify whether the original is overwritten or a new lineage is created |

If the system cannot resume, do not label a stopped task “paused.” If retrying may duplicate an external effect, first inspect the authoritative destination state.

## Place commitment around external effects

Separate these stages when their consequences differ:

```text
generate or propose -> user inspects -> authorize -> execute externally -> verify destination
```

A user's request to draft, summarize, or plan does not authorize sending, publishing, purchasing, deleting, changing permissions, or messaging another person. Before a consequential tool action, confirm the target, account, scope, payload, and reversibility using the applicable authorization rules.

After execution, verify the external system rather than trusting the model's narration. Preserve a durable record when the consequence warrants it.

## Make failure actionable

On interruption or failure, state:

1. What completed.
2. What did not complete.
3. Which partial output is retained and how trustworthy it is.
4. Which external actions, if any, already happened.
5. Whether the next action continues, retries, regenerates, edits, or starts over.

Avoid generic session, network, or tool errors without a recovery route. Preserve the user's input and completed work whenever safe.

## Support calibration and control

Expose sources, assumptions, uncertainty, model or data scope, and editability when they materially change how the result should be used. Scale explanation and user control to domain sensitivity and consequence rather than displaying confidence theatrically.

Useful research bases:

- Microsoft Guidelines for Human-AI Interaction: https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/
- Google PAIR Feedback + Control: https://pair.withgoogle.com/guidebook-v2/chapter/feedback-controls/

