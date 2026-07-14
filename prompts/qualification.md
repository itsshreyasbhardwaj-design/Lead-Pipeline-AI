# Qualification & Lead Scoring

## Purpose

Converts a research brief into a defensible, numeric qualification decision — should this lead be pursued now, nurtured, or deprioritized. This stage exists to stop AI-assisted prospecting from becoming "research everything, contact everything" and instead concentrate effort on leads with real probability of closing.

## Inputs

- `company-context.md` (required)
- The research brief output from `lead-research.md` for the target company
- `templates/lead-scoring-template.md` if you've customized scoring weights for your business (otherwise the default NBAT-plus model below is used)

## Outputs

```
## Lead Score: Company Name

| Dimension | Score (1–10) | Rationale |
|---|---|---|
| Need | | |
| Budget (likely ability to pay) | | |
| Authority (can we reach a real buyer) | | |
| Timing | | |
| Growth trajectory | | |
| Urgency | | |
| Likelihood to Buy | | |
| Overall ICP Fit | | |

Composite Score: X/80
Recommendation: Pursue Now / Nurture / Deprioritize
Reasoning: (2–4 sentences)
Confidence level: High / Medium / Low, with what would raise it
```

## Best Practices

- Score every dimension independently before computing a composite — resist the urge to reverse-engineer scores from a gut "this feels promising" reaction.
- A high Need score with a low Authority score (great pain, no reachable buyer) should not produce a high composite — flag it explicitly as "good fit, bad access" rather than averaging the problem away.
- State what evidence is missing that would move Confidence from Medium to High — this turns qualification into an actionable research task list, not just a verdict.
- Recalibrate score thresholds ("Pursue Now" = composite ≥ X) against your actual win-rate data once you have 20+ closed opportunities scored retroactively.

## Common Mistakes

- Scoring Budget based on company size alone — a well-funded company with a frozen budget for your category scores lower than a smaller company with active spend in your area; look for evidence (existing vendor spend, recent similar purchases), not just headcount.
- Letting "Overall ICP Fit" double-count the same evidence already scored under Need/Timing — Overall ICP Fit should reflect structural fit (industry, size, geography) independent of the moment-in-time signals.
- Producing a score with no accompanying reasoning — a number alone isn't actionable; the 2–4 sentence rationale is what a rep or the next stage actually uses.

## When to Use

Immediately after `lead-research.md`, before any outreach is drafted. Re-run after significant new information (a call, a reply, a new signal) to re-qualify.

## Example

**Input:** Research brief for "Cargofy" (see `lead-research.md` example).

**Output (excerpt):**
```
| Need | 8 | Active Kubernetes migration is a documented trigger for our core use case |
| Budget | 6 | Series C funded, but no confirmed existing spend in our category |
| Authority | 5 | VP Eng identified, but no confirmed warm path to reach them yet |
| Timing | 9 | Migration is in-flight now, not planned for later |
| Urgency | 7 | No stated deadline, but on-call pain compounds the longer migration continues |

Composite: 58/80 (approx. 7.25 avg)
Recommendation: Pursue Now
Reasoning: Strong need and timing alignment driven by a live, verifiable infrastructure
event. Authority is the main gap — prioritize finding a warm intro path or a more
senior sponsor before investing in a cold outbound sequence alone.
Confidence: Medium — would move to High with confirmation of budget ownership for
platform/observability tooling.
```
