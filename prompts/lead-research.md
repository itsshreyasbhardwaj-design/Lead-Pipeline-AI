# Lead Research

## Purpose

Builds a verified, structured profile of a target company and its likely decision-makers — the deepest research stage in the pipeline, and the foundation every later stage (qualification, outreach, meeting prep) depends on. This is where "spend 30 minutes researching a prospect" gets compressed without cutting the rigor.

## Inputs

- `company-context.md` (required)
- Target company name (required) and, if known, a specific contact name/title
- Any source material the user can supply or the model can access: company website, LinkedIn company page, recent news, job postings, funding databases, earnings calls/10-Ks (public companies), review sites (G2, Glassdoor), founder/exec social posts

## Outputs

A structured research brief:

```
## Company Snapshot
Business model / how they make money:
Target market / who they sell to:
Growth stage & recent trajectory:
Headcount (approx, with source):
Funding status (with source, if applicable):

## Buying Signals (only include if evidenced)
Signal — source — date — why it matters for us:

## Pain Points (mapped to our Company Context "What We Solve")
Likely pain — evidence or inference basis — confidence level:

## Decision-Making Landscape
Economic Buyer — name/title — confidence:
Champion candidate — name/title — confidence:
Technical/User Buyer — name/title — confidence:
Possible blockers/gatekeepers — confidence:

## Recent News / Public Signals
Item — source — date:

## What Could Not Be Verified
Explicitly list anything relevant but unconfirmed.
```

## Best Practices

- Cite a source (or "inferred from X") for every factual line — this is what separates this system from a chatbot guessing about a company.
- Prioritize signals that are recent (last 90 days) and specific over generic company facts (industry, size) that don't change the outreach angle.
- Map pain points explicitly back to the "What We Solve" section of Company Context — a research brief that doesn't connect to your offer is just trivia.
- When a decision-maker can't be identified with confidence, say so and suggest how to find them (e.g. "check LinkedIn for 'Head of X' at this company") rather than guessing a name.

## Common Mistakes

- Treating LinkedIn headcount or generic "About Us" copy as a buying signal — it isn't one; a signal is something time-bound and specific (a hire, a launch, a migration, a funding round, a stated initiative).
- Skipping the "What Could Not Be Verified" section — omitting it lets unverified claims quietly slip into outreach later.
- Researching the company but not mapping findings to pain points — this is the step that turns research into usable ammunition for the outreach stage.

## When to Use

Run immediately after `prospect-discovery.md` identifies a target, or as the first stage when the user already has a specific target company/contact in mind.

## Example

**Input:** Target company "Cargofy" (fictional), Company Context = DevOps SaaS company.

**Output (excerpt):**
```
## Company Snapshot
Business model: B2B freight logistics platform, enterprise SaaS + transaction fees
Recent trajectory: Raised $60M Series C (TechCrunch, March 2026); scaling engineering team

## Buying Signals
- 6 "Platform Engineer" job postings live on careers page (verified, checked directly) —
  suggests active infrastructure scaling, a common driver of our core use case
- Engineering blog post "Our Move to Kubernetes" published 3 weeks ago (verified,
  company blog) — direct match to our ICP's stated buying trigger

## Decision-Making Landscape
Economic Buyer: VP Engineering, name pulled from blog post byline (Verified)
Champion candidate: Platform Team Lead — could not confirm name (Unverified — suggest
  searching "Platform" + "Cargofy" on LinkedIn)

## What Could Not Be Verified
Current on-call tooling/vendor — no public evidence found; do not reference in outreach.
```
