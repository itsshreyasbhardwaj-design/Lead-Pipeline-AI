# CRM Notes & Next Best Action

## Purpose

Converts everything learned about a lead (research, qualification, outreach sent, replies received) into structured CRM-ready notes and a single clear next action. This is the stage that keeps a pipeline from living only in someone's memory or a scattered inbox.

## Inputs

- `company-context.md` (required)
- Research brief, qualification score, and outreach sent so far for this lead
- Any reply content or call notes, if available
- Current pipeline stage (e.g. Prospecting, Contacted, Meeting Booked, Opportunity, Closed Lost)

## Outputs

```
## CRM Note — [Company Name / Contact Name]

Stage: [current pipeline stage]
Lead Score: [from qualification.md, with date scored]
Summary: [2-3 sentence plain-language summary of where things stand]

Key Facts on Record:
- [Verified facts worth keeping on the account/contact record]

Interaction Log:
- [Date] — [Channel] — [What was sent/said] — [Outcome/response]

Next Best Action: [single, specific, dated action]
Owner: [who should do it]
Risk/Blocker (if any): [what could stall this deal, and suggested mitigation]
```

## Best Practices

- Keep the Summary genuinely plain-language — this note should be readable by someone who wasn't in the original research session (a manager, a teammate covering the account).
- The Next Best Action must be a single, concrete, schedulable action, not a vague "continue nurturing" — e.g. "Send follow-up 2 (resource angle) on [date]" or "Ask [name] for a warm intro to [economic buyer]."
- Log every outbound touch and every response, including non-responses after a full sequence — this is what makes qualification and sequencing decisions defensible later and prevents duplicate outreach from a teammate.
- Flag risk/blockers honestly (e.g. "no confirmed budget owner," "champion may be leaving role") rather than omitting anything that complicates a clean narrative.

## Common Mistakes

- Writing a CRM note that only restates the qualification score without an actual next action — the note should always end in something someone can do today.
- Losing the interaction history by overwriting old notes instead of appending to a log — CRM notes should read as a timeline, not a single snapshot.
- Marking a stage change (e.g. to "Opportunity") without the evidence that justifies it — stage should reflect verified buyer behavior (a meeting held, a next step confirmed), not optimism.

## When to Use

After every meaningful interaction: initial qualification, outreach sent, a reply received, a call held, or a stage change. Treat it as the closing step of every pipeline run.

## Example

```
## CRM Note — Cargofy / [VP Eng Name]

Stage: Contacted
Lead Score: 58/80 — Pursue Now (scored 2026-07-01)
Summary: Reached out on the Kubernetes migration signal; no reply yet after
initial email. LinkedIn connection request sent same day, accepted.

Interaction Log:
- 2026-07-01 — Email — Sent personalized outreach re: K8s migration — No reply
- 2026-07-01 — LinkedIn — Connection request sent — Accepted 2026-07-02

Next Best Action: Send Follow-up 2 (resource angle) on 2026-07-09 per sequence
in followups.md
Owner: [rep name]
Risk/Blocker: Authority not yet confirmed — VP Eng is a strong candidate but
budget ownership for observability tooling unverified. Consider a parallel
LinkedIn comment on their next relevant post to build warmth before follow-up 3.
```
