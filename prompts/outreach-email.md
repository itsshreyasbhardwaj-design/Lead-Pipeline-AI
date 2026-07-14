# Outreach Email

## Purpose

Writes a single, highly personalized cold email designed to earn a reply, not just a send. This is the stage most people mean when they say "write me a sales email" — but it only works well downstream of `lead-research.md` and `qualification.md`; run in isolation without real research, it will default to generic (and get flagged as such).

## Inputs

- `company-context.md` (required)
- Research brief for the target company/contact from `lead-research.md` (required — do not run this stage on a bare company name with no research)
- Target contact name, title, and any direct personalization source (a post they wrote, a talk they gave, a specific company event)
- Optional: which pain point from Company Context to lead with, if the user wants to control angle

## Outputs

A single email:

```
Subject: [max 9 words, specific — never "Quick question" or "Following up"]

[Body — 60–120 words]
[Personalized opening: 1–2 sentences proving real research, tied to a verified signal]
[Bridge: 1–2 sentences connecting that signal to a pain point from Company Context]
[Value: 1 sentence — proof point or result, specific not generic]
[CTA: 1 sentence, single clear ask, low-friction]

[Sign-off]
```

Plus a one-line note on which Company Context pain point and which research signal were used, so the user can sanity-check the personalization.

## Best Practices

- The first sentence must reference something true and specific about the prospect — pulled directly from the research brief, never invented. If the research brief has fewer than three genuine personalization points, say so and ask whether to proceed with what's available or wait for more research.
- Keep it under 120 words. Length signals mass-production; brevity signals a busy person who did their homework and respects the reader's time.
- One CTA only. "Worth a quick call?" beats "Let me know if you'd like to hop on a call, or I'm happy to send more info, or feel free to reply with questions" — multiple asks reduce reply rate.
- Write the subject line last, after the body — it should reflect the specific hook used, not a generic template.
- Read the email aloud (mentally) as the recipient. If it could be sent to any company in the ICP by swapping the name, rewrite it — this is the single-highest-value self-check in the whole system.

## Common Mistakes

- Leading with "I noticed you're the VP of Engineering at [Company]" — restating public, obvious facts is not personalization; it signals a template.
- Using the banned-phrase list from the system prompt ("Hope you're doing well," "Just following up," etc.) — these are the clearest AI/mass-email tells.
- Stacking multiple value props in one email — pick the single pain point most supported by evidence and go deep on it, not wide.
- Ending with a vague CTA ("Let me know your thoughts") instead of a specific, low-friction one ("Worth 15 minutes next Tuesday or Wednesday?").

## When to Use

After `lead-research.md` and `qualification.md` have confirmed the lead is worth pursuing now. Never run cold, without a research brief.

## Example

**Input:** Research brief + qualification for "Cargofy" (VP Engineering, Kubernetes migration signal), Company Context = DevOps observability SaaS.

**Output:**
```
Subject: Cargofy's move to Kubernetes and on-call load

Hi [Name],

Saw the engineering blog post on Cargofy's move from ECS to Kubernetes — that
transition window is usually when alert noise spikes 3-4x before tooling
catches up.

We built [Product] for exactly that phase: cut alert-to-resolution time by
40% for two other logistics-platform teams mid-migration, without adding a
dashboard your team has to babysit.

Worth 15 minutes next week to see if the timing lines up?

[Name]
```
Note: Opening uses the verified blog-post signal from research; bridges to the
"on-call load during infra transitions" pain point in Company Context; single CTA.
