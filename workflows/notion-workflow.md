# Notion Workflow

## What Notion is for in this pipeline

Notion works well as a lightweight, flexible pipeline tracker for individuals, small teams, or anyone not yet ready to invest in a full CRM (HubSpot/Salesforce) — a single database that mirrors the `crm.md` structure and gives visibility across the whole team.

## Data handoff points

**This system → Notion:**
- Build a Notion database with properties mirroring `templates/crm-template.md`: Company, Stage, Lead Score, Next Best Action (with a date property), Owner.
- Store each lead's research brief (`lead-research.md` output), qualification rationale (`qualification.md` output), and generated outreach (`outreach-email.md`, `followups.md`) as sub-pages or long-text properties on that lead's database row, so the full research and messaging history lives alongside the tracking record.

**Notion → this system:**
- When re-qualifying a Nurture lead or prepping for a meeting, pull the existing Notion page content directly as input to `meeting-prep.md` or a re-run of `qualification.md`, rather than re-researching from scratch.

## Setup

1. Create a Notion database with these properties at minimum: Company (title), Contact Name, Stage (select, matching `crm.md` stages), Lead Score (number), Next Best Action (text), Next Action Date (date), Owner (person).
2. For each lead, create a page and paste in: the research brief, qualification score with rationale, generated outreach, and a running interaction log (can use a toggle list or a simple bulleted log matching the `crm.md` format).
3. Use Notion's board/table views filtered by Stage and sorted by Next Action Date as your daily working view — this becomes your lightweight pipeline dashboard.
4. For team use, add a "Last Updated" or "Last Contacted" date property and build a filtered view surfacing leads that haven't been touched in your defined follow-up window, to catch stalled leads.

## Gotchas

- Notion has no native email-sending or sequencing capability — pair it with `gmail-workflow.md` or `instantly-workflow.md` for actual sending, using Notion purely as the system of record.
- At high lead volume (hundreds+ actively worked leads), a dedicated CRM (`hubspot-workflow.md`, `salesforce-workflow.md`) will scale better than Notion's database performance and reporting — Notion is best suited to early-stage or smaller-volume pipelines.
- Notion AI is a separate product from this system's prompts — if you use Notion AI for drafting, still run outputs through this system's stage prompts (loaded with your `company-context.md`) to preserve the accuracy and personalization discipline documented in `docs/prompt-guide.md`.
