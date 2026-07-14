# Gmail Workflow

## What Gmail is for in this pipeline

For individual reps, small teams, or lower-volume/high-touch motions (e.g. the Agencies or Healthcare examples in `/examples`, where volume is lower and personalization depth matters even more), sending directly from Gmail rather than a dedicated cold email tool is often the right choice — better deliverability for low volume, and a more natural reply experience for the prospect.

## Data handoff points

**This system → Gmail:**
- Copy the generated email from `outreach-email.md` directly into a Gmail draft or Gmail's built-in scheduled send.
- For the five-touch sequence from `followups.md`, use Gmail's "Schedule send" on each message at the suggested intervals, or set reminders to send manually if you want to adjust based on real engagement (opens are not reliably trackable in plain Gmail without a tracking extension).

**Gmail → this system:**
- Reply content and thread context should be pasted into `crm.md` as new Interaction Log entries and into `objection-handling.md` if a reply raises a specific concern to address.

## Setup

1. If sending any real volume (10+ per day) from a primary work Gmail account, warm up gradually and monitor for deliverability issues — Google Workspace accounts have sending limits and reputation considerations.
2. Use Gmail's built-in "Schedule send" to space the follow-up sequence from `followups.md` without needing a separate tool.
3. Set up a simple label system (e.g. "Pipeline/Contacted," "Pipeline/Replied," "Pipeline/Meeting Booked") mirroring the Stage field in `crm.md`, so your inbox stays a rough mirror of pipeline state even without a dedicated CRM.
4. For teams, consider a shared label/thread convention or a lightweight shared tracker (see `notion-workflow.md`) alongside individual Gmail sending, since Gmail alone doesn't give team-wide pipeline visibility.

## Gotchas

- Gmail has daily sending limits (varies by account type and standing) — this is a hard constraint on batch size regardless of how many qualified leads `qualification.md` surfaces in one run.
- No native open/click tracking without a third-party extension — if engagement data matters for your follow-up timing decisions, either add a tracking extension (mind prospect trust/privacy implications) or rely on reply-based signals only.
- Gmail is best suited to genuinely 1:1, high-personalization outreach at moderate volume — for larger-scale campaigns, prefer `instantly-workflow.md` for dedicated sending infrastructure.
