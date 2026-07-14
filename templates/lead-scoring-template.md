# Lead Scoring Template

The default scoring model used by `prompts/qualification.md`. Copy and customize this if your business needs different dimensions or weights — see `docs/configuration.md#configuring-scoring-weights`.

```markdown
## Scoring Dimensions (default: equal weight, 1–10 each)

| Dimension | What it measures | 1–3 (Weak) | 4–7 (Moderate) | 8–10 (Strong) |
|---|---|---|---|---|
| Need | Evidence the pain we solve actually exists for them | No evidence of pain | Plausible inference, unconfirmed | Directly confirmed via research or their own words |
| Budget | Likely ability/willingness to pay at our price point | No spend signal, resource-constrained | Adequate size/funding, spend unconfirmed | Confirmed existing spend in category or clear budget authority |
| Authority | Can we realistically reach a real buyer | No identified path to any buyer | Buyer identified, no access path | Buyer identified with a warm path or existing relationship |
| Timing | Is this urgent/live now vs. hypothetical later | No timing signal | Plausible near-term relevance | Active, time-bound trigger event confirmed |
| Growth trajectory | Is the company positioned to be a bigger opportunity over time | Flat/declining | Stable | Actively scaling in ways relevant to us |
| Urgency | How costly is inaction for them | Low/no visible cost | Moderate, ongoing cost | High, compounding, or deadline-driven cost |
| Overall ICP Fit | Structural fit independent of time-bound signals | Poor firmographic/technographic match | Partial match | Strong match across ICP criteria |

## Composite and Recommendation Thresholds (defaults — recalibrate against your own win-rate data)

Composite = sum of all seven scores (max 70) — adjust the max if you add/remove dimensions.

- 56–70: Pursue Now
- 35–55: Nurture (revisit on a cadence or new signal)
- Below 35: Deprioritize

## Custom Weighting (optional)

If dimensions should carry unequal weight for your business, define multipliers here, e.g.:

Authority weight: 1.5x (enterprise motion — access is the primary bottleneck)
Timing weight: 1.5x (seasonal business — off-cycle leads are structurally lower-value regardless of other scores)

Recompute composite as weighted sum ÷ weighted max, scaled back to a comparable range.
```
