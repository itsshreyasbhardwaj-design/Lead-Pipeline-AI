# Follow-Up Sequences

## Purpose

Generates a five-touch follow-up sequence for a prospect who hasn't replied to the initial outreach. The core rule this stage enforces: every follow-up must introduce genuinely new value or a new angle — never a rephrased "just bumping this up."

## Inputs

- `company-context.md` (required)
- The original outreach email/message from `outreach-email.md` (required, so follow-ups don't repeat its angle)
- Research brief from `lead-research.md` (for additional angles to draw on)
- Optional: any reply/non-reply behavior observed (opened but didn't reply, clicked a link, etc.) if the sending tool provides it

## Outputs

Five follow-up messages, each labeled with its distinct angle and suggested timing:

```
## Follow-up 1 (Day 3-4) — Angle: [e.g. new proof point]
[Message, 40-80 words]

## Follow-up 2 (Day 7-8) — Angle: [e.g. relevant resource/insight]
[Message]

## Follow-up 3 (Day 12-14) — Angle: [e.g. different stakeholder/use case]
[Message]

## Follow-up 4 (Day 18-21) — Angle: [e.g. direct/permission-based close]
[Message]

## Follow-up 5 (Day 28-30) — Angle: [e.g. break-up/final value drop]
[Message]
```

## Best Practices

- Each message must lead with a genuinely different piece of value: a new proof point, a relevant resource, a different pain angle, a different stakeholder's perspective, a timely news hook — never a rephrase of "wanted to follow up on my last email."
- Shorten as the sequence progresses — early follow-ups can be 60-80 words, later ones tighten to 40-60 as the relationship-building budget shrinks.
- The final message in the sequence should be a genuine, low-pressure "breakup" that gives the prospect an easy out and, counterintuitively, often drives the highest reply rate of the sequence.
- Space timing to avoid appearing automated — irregular gaps (3, 4, 5, 6, 10 days) read more human than a rigid weekly cadence, though exact timing should adapt to the user's sequencing tool.

## Common Mistakes

- Writing five variations of "just checking in" — this is the single most common failure mode and the fastest way to get marked as spam.
- Escalating pressure/urgency across the sequence ("last chance," "final reminder") — this reads as manipulative rather than genuinely helpful, and undermines the consultative tone established in the first email.
- Reusing the exact proof point or research signal from the original outreach email — if follow-up 1 repeats the hook from the first email, it wastes the prospect's second read.

## When to Use

Generate immediately after `outreach-email.md`, so the full sequence is planned upfront and loaded into a sequencing tool (see `/workflows`) rather than improvised message-by-message.

## Example

**Follow-up 2 (Day 7-8) — Angle: relevant resource**
```
Subject: Re: Cargofy's move to Kubernetes and on-call load

[Name] — no pressure on the last note. In case useful regardless of timing,
we put together a short breakdown of the three most common alert-noise
sources teams hit in the first month post-migration. Happy to send it over,
or skip straight to a quick call if that's more useful.
```
