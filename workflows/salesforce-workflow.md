# Salesforce Workflow

## What Salesforce is for in this pipeline

Salesforce is the enterprise-standard CRM — use it as the system of record when your organization already runs on Salesforce, particularly for teams with more complex approval processes, multiple sales motions, or existing Salesforce-native tooling (Sales Cloud, Pardot/Account Engagement, etc.).

## Data handoff points

**This system → Salesforce:**
- Create/update Account and Contact (or Lead, pre-conversion) records for each prospect that clears `qualification.md`.
- Map `crm.md` fields to Salesforce: Stage → Opportunity Stage (or a custom Lead Status if still pre-Opportunity), Lead Score → a custom field on the Lead/Contact object, Interaction Log → Salesforce Activities (Tasks/Events) or a custom related list, Next Best Action → an assigned Task with ActivityDate set to the specified date.
- Generated outreach content can be stored as a Note/Attachment on the record or pushed into a connected sequencing tool (Salesloft, Outreach.io, or Salesforce's native Sales Engagement if licensed) for actual sending.

**Salesforce → this system:**
- Pull existing Account/Contact/Opportunity history as input to `lead-research.md` and `meeting-prep.md` when working an account with prior Salesforce history, so research builds on institutional knowledge instead of starting fresh.
- Opportunity stage history and close/loss reasons should inform recalibration of `qualification.md` thresholds over time, per `docs/best-practices.md#lead-qualification-discipline` — Salesforce reporting is the natural source for this analysis given enough closed-deal volume.

## Setup

1. If your org doesn't already have one, work with your Salesforce admin to add a custom Lead Score field (Number, 0–70) and, if useful, a custom picklist reflecting this system's qualification recommendation (Pursue Now / Nurture / Deprioritize).
2. Align Opportunity Stages (or Lead Status values, if working pre-conversion) with the stages in `crm.md` — exact naming can follow your org's existing conventions, but ensure a clean mapping exists so `crm.md` output can be logged without translation ambiguity.
3. If using Salesforce's native Sales Engagement or a connected sequencing tool, build the sequence template structure to match the 5-touch pattern from `followups.md`, populating each step with the generated, personalized content per contact.
4. Establish a Task-creation habit (manual or via Flow automation) so every `crm.md` Next Best Action becomes a real, assigned, dated Salesforce Task.

## Gotchas

- Salesforce customization (custom fields, Flows, page layouts) typically requires admin access — coordinate with your Salesforce admin before building out the field mapping above, especially in orgs with existing complex automation that could conflict.
- Lead-to-Contact/Account conversion timing varies by org convention — clarify at what pipeline stage (per `crm.md`) your org expects conversion, and align this system's stage usage accordingly.
- Large orgs often have existing lead scoring or routing automation (e.g. via Pardot/Account Engagement) — ensure this system's Lead Score field is clearly differentiated (e.g. "AI Qualification Score") from any existing marketing-qualified-lead scoring to avoid confusion between the two.
