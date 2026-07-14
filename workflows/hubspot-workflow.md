# HubSpot Workflow

## What HubSpot is for in this pipeline

HubSpot is a full CRM — use it as the system of record for contacts, companies, deals, and sequences once your pipeline outgrows a lightweight tracker like Notion, and as the sending/sequencing layer via HubSpot Sequences.

## Data handoff points

**This system → HubSpot:**
- Create or update a HubSpot Company and Contact record for each lead that clears `qualification.md`'s "Pursue Now" threshold.
- Map `crm.md` output fields to HubSpot properties: Stage → Deal Stage (custom pipeline recommended, matching this system's stages), Lead Score → a custom numeric or picklist property, Interaction Log → logged Activities/timeline entries, Next Best Action → a HubSpot Task with the specified due date and owner.
- Load generated outreach from `outreach-email.md` and `followups.md` into a HubSpot Sequence, using personalization tokens only for structural fields (first name, company) — keep the researched personalized opening as hand-placed text per contact.

**HubSpot → this system:**
- Pull existing HubSpot Company/Contact data (industry, headcount if enriched, deal history, prior interactions logged by the team) as a starting input to `lead-research.md` when re-engaging an existing HubSpot record, so research doesn't start from zero on accounts your team has already touched.
- Engagement data (email opens, sequence replies, meeting bookings) logged in HubSpot should inform `crm.md` updates and `qualification.md` re-scoring.

## Setup

1. Create a custom deal pipeline (or reuse HubSpot's default, renamed) with stages matching `crm.md`: Prospecting, Contacted, Meeting Booked, Opportunity, Proposal Sent, Closed Won, Closed Lost, Nurture.
2. Add a custom Lead Score property (number, 0–70 to match `templates/lead-scoring-template.md`'s default scale) at the Contact or Deal level.
3. Build a Sequence template structure matching the 5-touch pattern from `followups.md`, with placeholder steps you fill in per-contact with the generated, personalized content rather than a single generic template sequence.
4. Set up a HubSpot Task automation or manual routine so every `crm.md`-generated Next Best Action becomes an actual assigned Task with a due date — this is what keeps the CRM record driving real daily work rather than becoming a static log.

## Gotchas

- HubSpot Sequences have their own personalization-token system — don't let token-based personalization ("Hi {{firstname}}, I saw you work at {{company}}") substitute for the deep, research-based personalization this system produces; use tokens only for structural fields, keep the substantive opening hand-placed.
- HubSpot plan tier affects available custom properties, pipeline count, and Sequences access — verify your tier supports the field mapping above before building it out.
- Sync carefully if HubSpot is also connected to marketing automation for inbound leads — make sure outbound pipeline stages (from this system) and inbound lead stages don't collide in a way that causes accidental disqualification or duplicate outreach.
