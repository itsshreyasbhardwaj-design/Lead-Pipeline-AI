# Clay Workflow

## What Clay is for in this pipeline

Clay (clay.com) is a data enrichment and workflow-automation tool that pulls from many data sources (Apollo, Clearbit, LinkedIn, news APIs, and more) into one table, with built-in AI columns. Use it as the enrichment layer that feeds `lead-research.md` with pre-aggregated, multi-source data, and optionally to automate parts of the discovery-to-research handoff.

## Data handoff points

**Clay → this system:**
- Build a Clay table with enrichment columns (company news, job postings, funding, headcount, technographic data, LinkedIn activity) for your target list, then export or summarize each row as structured input to `lead-research.md` — this gives the research stage a running start instead of starting from a bare company name.
- Clay's built-in AI columns can pre-draft a first-pass signal summary per company; treat this as a first draft that `lead-research.md` verifies and structures per this system's accuracy contract, not a final research brief.

**This system → Clay:**
- Once a research brief and qualification score exist, write them back into the corresponding Clay table row (as custom columns) so your enriched table becomes the full pipeline record, not just a data source.
- Generated outreach from `outreach-email.md` can be added as a column and pushed from Clay into your sending tool (Instantly, Smartlead, or a native email integration) via Clay's outbound integrations.

## Setup

1. Build a Clay table sourced from your ICP-matching list (import from a CSV, Apollo search, or LinkedIn Sales Navigator export via Clay's integrations).
2. Add enrichment columns for the specific signals your Company Context's Buying Triggers section defines (e.g. "recent funding," "relevant job postings," "recent blog/news mentions").
3. Use Clay's AI column feature to pre-summarize findings per row, but always run the row through `lead-research.md` before using it for outreach — Clay's automated summaries don't apply this system's Verified/Inferred/Assumed labeling discipline by default.
4. Add output columns for Qualification Score, Outreach Email, and CRM Note so the table becomes a full working pipeline view your team can filter and sort by.

## Gotchas

- Clay's per-enrichment-source credit costs add up quickly at scale — prioritize enrichment depth for your top-scored, highest-intent prospects rather than enriching an entire raw list uniformly.
- Different Clay data sources have different freshness/accuracy — always note the source and date when carrying a Clay-sourced fact into `lead-research.md`, consistent with this system's citation discipline.
- Clay's AI columns run on whatever model is configured in your workspace — for consistency with this system's accuracy standards, prefer using Clay for raw data aggregation and doing the actual research synthesis in your primary Claude session/project using `lead-research.md`.
