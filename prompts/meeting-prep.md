# Meeting Prep

## Purpose

Produces a pre-call briefing for a discovery call, demo, or follow-up meeting — consolidating research, qualification, and prior interactions into what the rep actually needs in the ten minutes before a call, plus a discovery question set tailored to the specific account.

## Inputs

- `company-context.md` (required)
- Research brief, qualification score, and CRM notes/interaction log for this lead
- Meeting type: first discovery call, demo, technical deep-dive, negotiation/closing call
- `templates/discovery-questions.md` if a standard question bank exists to draw from

## Outputs

```
## Meeting Prep — [Company Name] — [Meeting type] — [Date]

60-Second Briefing:
[Who they are, why they're a fit, what's happened so far, in plain language]

Attendees (known/expected):
[Name — Title — Role in decision (Economic Buyer/Champion/Technical/User) — Confidence]

Goals for This Meeting:
1. [Primary objective]
2. [Secondary objective]

Discovery Questions (prioritized):
1. [Open-ended question tied to their specific likely pain point]
2. ...

Anticipated Objections & Ready Responses:
[Pulled from objection-handling.md logic — objection, reframe, evidence]

Proof Points to Have Ready:
[Specific to their industry/use case from Company Context Social Proof]

Recommended Next Step to Propose at Close of Call:
[Specific, e.g. "propose a technical deep-dive with their platform lead"]
```

## Best Practices

- Keep the 60-Second Briefing genuinely scannable in 60 seconds — this is meant to be read walking into the call, not studied in advance.
- Order discovery questions from broad/open to specific — start with questions that let the prospect reveal priorities in their own words before narrowing toward your specific solution area.
- Pull anticipated objections from patterns in Company Context, not a generic objection list — if this account looks price-sensitive (small company, early stage) versus risk-sensitive (enterprise, regulated industry), prep different objections accordingly.
- Always end with a recommended next step — a meeting without a proposed next step tends to stall regardless of how well it went.

## Common Mistakes

- Producing a generic discovery question list that isn't adapted to what's already known about this specific account — if research already surfaced a likely pain point, questions should probe and confirm it, not start from zero.
- Omitting attendee role/confidence — walking into a call without a clear read on who's the economic buyer versus an influencer leads to misjudging the room.
- Skipping proof points relevant to their specific vertical/use case in favor of generic company-wide stats.

## When to Use

Before any scheduled call, once a meeting is booked via outreach or follow-up.

## Example (excerpt)

```
60-Second Briefing: Cargofy, 400-person logistics tech company, Series C.
Reached out on their Kubernetes migration (verified via engineering blog).
VP Engineering [name] accepted LinkedIn connection, replied positively to
follow-up 2, booked this 20-min intro call. Lead score 58/80 — Pursue Now.
Authority not fully confirmed — this call should clarify budget ownership.

Discovery Questions (prioritized):
1. "How's the Kubernetes migration going on the operational side — has
   on-call load shifted the way you expected?"
2. "Who else is involved in evaluating observability/tooling decisions on
   your team right now?"
3. "What's currently the biggest source of alert noise for your platform team?"
```
