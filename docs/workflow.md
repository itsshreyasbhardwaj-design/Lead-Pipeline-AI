# The Full Workflow

This document describes how to chain individual stages into one continuous pipeline run per lead — the difference between using this system as a set of disconnected tools versus a real pipeline.

## The full sequence

```
1. prospect-discovery.md   → ranked list of target companies
2. lead-research.md        → verified research brief (per company)
3. qualification.md        → lead score + Pursue/Nurture/Deprioritize
4. outreach-email.md       → first email (only if "Pursue Now")
5. linkedin.md              → parallel/complementary channel touch
6. followups.md            → 5-touch sequence, generated upfront
7. crm.md                   → structured notes + next action
   ↳ (on reply or new information) → objection-handling.md and/or
     meeting-prep.md → proposal.md
   ↳ crm.md re-run after every meaningful interaction
```

## Why this order

- **Discovery before research** — don't spend deep research time on companies that don't clear a basic ICP/signal bar first.
- **Research before qualification** — you can't score Need, Budget, Authority, or Timing without evidence; scoring without research is guessing.
- **Qualification before outreach** — this is the gate that prevents wasted, low-quality outreach. Only "Pursue Now" leads should proceed to outreach; "Nurture" leads should be revisited later (see below), and "Deprioritize" leads should stop here.
- **Follow-ups generated upfront, not improvised** — planning the full 5-touch sequence at once (right after the first email) ensures each touch has a distinct angle instead of being invented reactively under time pressure.
- **CRM notes after every interaction, not just at the end** — this is what makes the pipeline auditable and handoff-ready, and what feeds the Next Best Action that keeps deals moving.

## Handling "Nurture" leads

Leads scored "Nurture" in `qualification.md` shouldn't be dropped — they should be revisited on a cadence (e.g. monthly) or triggered by a new buying signal. Re-run `lead-research.md` periodically for nurture-stage accounts to check for new signals, and re-run `qualification.md` when something changes. This system does not currently include an automated re-engagement stage — see `ROADMAP.md`; in the meantime, track nurture leads in your CRM (`crm.md` output) with a scheduled next-check date.

## A single lead, start to finish

**Example run for one prospect, "Cargofy":**

1. Discovery surfaced Cargofy from a list of 40 companies (High signal strength)
2. Research brief built: Kubernetes migration signal, VP Eng identified
3. Qualification: 58/80, Pursue Now, Authority flagged as the gap to close
4. Outreach email sent, referencing the migration signal
5. LinkedIn connection request sent same day
6. Five-touch follow-up sequence generated and loaded into sequencing tool
7. CRM note logged after each touch; reply received on follow-up 2
8. Objection raised on the call ("we already have an APM tool") — handled using `objection-handling.md`
9. Meeting booked — `meeting-prep.md` run before the call
10. Strong discovery call — `proposal.md` run to draft next-step document
11. CRM note updated to "Opportunity" stage with proposal sent as Next Best Action's outcome

## Running this for many leads at once (batch mode)

For a batch of prospects from one discovery run, the recommended pattern is:

1. Run `prospect-discovery.md` once to get the ranked list.
2. Run `lead-research.md` and `qualification.md` for each company in the list, working top-down by priority.
3. Only run `outreach-email.md` onward for leads that score "Pursue Now" — this keeps effort concentrated on your best opportunities rather than spreading thin across the full list.
4. Track all leads (including Nurture and Deprioritized) in `crm.md` notes so the full list stays visible for future re-qualification.

## Orchestrating programmatically

If you want to automate this chaining rather than running it conversationally, see `docs/customization.md#programmatic-orchestration` and the `ROADMAP.md` entry on a reference Python implementation. The prompts themselves are designed to be called programmatically (structured inputs/outputs) even though the primary intended usage is conversational.
