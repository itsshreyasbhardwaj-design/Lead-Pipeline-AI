# Roadmap

This roadmap tracks where Lead Pipeline AI is headed. Priorities are driven by what makes the system more useful in production, not feature count. Items move from **Proposed** to **In Progress** once an issue is opened and a contributor is assigned; see `CONTRIBUTING.md`.

## Now (v1.x)

- [ ] Expand `/examples` to 10+ industries (Real Estate, Financial Services, Legal, Recruiting, Nonprofit/Fundraising)
- [ ] Add `pipedrive-workflow.md`, `outreach.io-workflow.md`, `smartlead-workflow.md`
- [ ] Add a `prompts/re-engagement.md` stage for dormant/closed-lost leads
- [ ] Add a `prompts/referral-request.md` stage for post-close referral generation
- [ ] Community-contributed prompt evaluation rubric (how to score whether an outreach email is "good") in `docs/best-practices.md`

## Next (v2.0)

- [ ] Multilingual prompt variants (Spanish, Portuguese, French) with localization notes on tone/formality norms
- [ ] Account-based marketing (ABM) mode: multi-threading prompts for reaching several stakeholders at one target account in a coordinated sequence
- [ ] Partner/channel outreach variant (different qualification and messaging logic than direct sales)
- [ ] A lightweight, optional Python reference implementation that chains the prompts programmatically against the Claude API (kept separate from the core prompt library so the repo stays framework-agnostic)

## Later (exploratory)

- [ ] Voice/call-script generation stage for outbound calling teams
- [ ] Event and conference outreach workflow (pre-event, at-event, post-event sequences)
- [ ] Integration workflow for warm intro / mutual-connection sourcing

## Non-goals

- This project will not become a hosted SaaS product or require a backend to function. It stays a prompt + documentation library that runs inside tools you already use.
- This project will not bundle scraping tools that violate target platforms' terms of service.

Have an idea not listed here? Open an issue using the **Feature Request** template.
