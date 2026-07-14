# CRM Note Template

The structure used by `prompts/crm.md`, provided standalone for manual use or for mapping directly into a CRM's custom fields (see `/workflows` for tool-specific field mapping, e.g. `workflows/hubspot-workflow.md`).

```markdown
## CRM Note — [Company Name / Contact Name]

Stage: [Prospecting / Contacted / Meeting Booked / Opportunity / Proposal Sent / Closed Won / Closed Lost / Nurture]
Lead Score: [X/70, date scored]
Summary: [2-3 sentences, plain language]

Key Facts on Record:
-
-

Interaction Log:
- [Date] — [Channel: Email/LinkedIn/Call/Meeting] — [What happened] — [Outcome]
- [Date] — [Channel] — [What happened] — [Outcome]

Next Best Action: [specific, dated, ownable]
Owner:
Risk/Blocker:

## Field Mapping Notes (for CRM integration)
Stage → maps to your CRM's deal/pipeline stage field
Lead Score → custom numeric field, or mapped to a Hot/Warm/Cold picklist
Interaction Log → CRM activity/timeline entries (one entry per log line)
Next Best Action → CRM task with due date
Owner → CRM task assignee
```
