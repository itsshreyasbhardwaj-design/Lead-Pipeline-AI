# Company Context — Master Input File

## Purpose

This is the single most important file in the entire system. Every prompt in `/prompts` is instructed to read it before producing output. It captures everything an AI needs to know about *your* business to reason like an insider instead of a generic copywriter: who you sell to, what you sell, why you win, and how you sound. Fill it out once, revisit it quarterly, and every downstream stage — research, qualification, outreach, follow-ups — improves automatically.

This file is a **template**. A ready-to-copy blank version with inline instructions also lives at `templates/company-context-template.md` — they are kept identical; this copy lives in `/prompts` so it's visible alongside the stages that consume it.

## Inputs

None — this is an input file you fill out, not a prompt you run.

## Outputs

A single completed Markdown file (`company-context.md`) that you load into every session, project, or workflow alongside the pipeline prompts.

## Best Practices

- Be specific. "Mid-market" is weaker than "50–500 employees, Series A–C, US and UK." Specificity is what lets the AI qualify and personalize instead of guessing.
- Write your ICP from won-deal patterns if you have any closed customers — real pattern beats hypothetical persona every time.
- Update this file after every 10–20 closed/lost deals as your understanding of what works sharpens.
- Keep Brand Voice concrete: list 3 words you are and 3 words you are explicitly not.

## Common Mistakes

- Leaving "Ideal Customer" as an industry name only ("SaaS companies") with no size, stage, or buying-trigger detail — this produces generic qualification and generic outreach.
- Copying competitor positioning instead of your own — the AI will then write outreach that sounds like your competitor, not you.
- Skipping the "What We Solve" section — without explicit pain points, every email defaults to feature-listing instead of problem-first framing.

## When to Use

Fill out before running any other stage. Revisit and update quarterly or after a strategy shift.

---

## Template

```markdown
# COMPANY CONTEXT

## Company Overview
Company Name:
One-line description (what you do, for whom):
Website:
Founded / Stage (bootstrapped, seed, Series A, established, etc.):
Team size:

## What We Sell
Product/Service name(s):
Core offering in plain language (no jargon):
Pricing model (subscription, usage-based, project-based, retainer, etc.):
Typical price point / deal size:

## Ideal Customer Profile (ICP)
Industry / verticals:
Company size (employees and/or revenue):
Geography:
Company stage/maturity (startup, growth, enterprise, etc.):
Technographic signals (tools/stack they likely use, if relevant):
Buyer roles / titles who typically initiate a purchase:
Buyer roles / titles who typically approve budget:

## What We Solve
Top 3–5 pain points our best customers had before buying:
1.
2.
3.
What happens if this pain goes unsolved (cost of inaction):
Why existing alternatives (status quo, competitors, in-house) fall short:

## Unique Advantages
What we do that competitors/alternatives don't:
Proof points (results, case studies, benchmarks, certifications):
Named competitors or alternatives we're most often compared to:

## Brand Voice
3 words we are:
3 words we are explicitly not:
Tone guidance (formal/casual, technical/plain, etc.):
Anything we never say or do in outreach:

## Buying Triggers
Events/signals that indicate someone is ready to consider us (e.g. new funding,
leadership change, hiring surge in a relevant function, product launch,
compliance deadline, contract renewal window, seasonal cycle):
1.
2.
3.

## Success Metrics
What we're optimizing pipeline for right now (e.g. meetings booked, demo
requests, partnership conversations, paid signups):

## Objections We Hear Most Often
1. Objection — how we typically reframe it:
2. Objection — how we typically reframe it:
3. Objection — how we typically reframe it:

## Social Proof
Notable customers (that we're allowed to name publicly):
Quantified results we can cite (e.g. "reduced X by 40% for Y"):
Testimonial quotes available for reuse:
```
