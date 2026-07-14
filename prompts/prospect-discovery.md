# Prospect Discovery

## Purpose

Generates a prioritized list of companies (and, where possible, named roles) that match your Ideal Customer Profile, ranked by fit and buying-signal strength. This is the entry point of the pipeline when you don't already have a target list — it turns "who should we even be talking to" into a working list ready for `lead-research.md`.

## Inputs

- `company-context.md` (required) — specifically the Ideal Customer Profile and Buying Triggers sections
- A sourcing pool: either a market/vertical to search within, a list of company names to filter and rank, or access to a data source (LinkedIn Sales Navigator export, Apollo/Clay export, a conference attendee list, etc.) pasted or described
- Optional: a target count (e.g. "give me 20") and any hard exclusions (competitors, existing customers, do-not-contact list)

## Outputs

A ranked table of prospect companies with:

| Company | Why it fits ICP | Buying signal(s) observed | Signal strength (High/Med/Low) | Confidence (Verified/Inferred) | Suggested next step |

Followed by a short rationale for the top 3–5 picks explaining why they're prioritized above the rest.

## Best Practices

- Rank by **signal strength + ICP fit combined**, not ICP fit alone — a perfect-fit company with zero buying signal is a worse near-term target than a good-fit company that just raised funding or posted 5 relevant job openings.
- Cap the list at a size the user can actually research and contact well (20–30, not 500) — this system optimizes for quality per lead, not volume.
- When working from a described market rather than a data export, explicitly state that company-level facts (funding, headcount) need verification in the next stage — discovery produces candidates, not verified profiles.
- Always exclude known customers and named competitors from `company-context.md` unless the user asks otherwise.

## Common Mistakes

- Presenting an unranked list — the entire value of this stage is prioritization, not just listing companies that vaguely match an industry.
- Inventing buying signals ("likely expanding") without a stated basis — if no real signal is available, say "no strong signal identified" rather than fabricating one.
- Ignoring stated exclusions (competitors, existing customers) from Company Context.

## When to Use

First stage, when you need to build or refresh a target list. Skip this stage if the user already has a specific target company in mind — go straight to `lead-research.md`.

## Example

**Input:** Company Context = mid-market DevOps SaaS company (ICP: 100–1,000 employee tech companies, US/UK, VP Engineering or CTO as buyer). Sourcing pool: "here are 40 companies from our Series B+ tech company list" (pasted list).

**Output (excerpt):**

| Company | Why it fits ICP | Buying signal(s) | Strength | Confidence | Next step |
|---|---|---|---|---|---|
| Flexport-style logistics co (fictional: "Cargofy") | 400 employees, Series C, US-based tech-forward logistics | 6 open "Platform Engineer" reqs posted in last 30 days; blog post on Kubernetes migration | High | Verified (job board + blog) | Move to research — target VP Eng named in blog post byline |
| Fictional co "Northline Freight" | 220 employees, matches size band | No public signals found | Low | N/A | Deprioritize unless referral available |

Rationale: Cargofy is prioritized first because the Kubernetes migration signal directly maps to our ICP's core buying trigger (infrastructure transitions increase on-call load, which is our core wedge).
