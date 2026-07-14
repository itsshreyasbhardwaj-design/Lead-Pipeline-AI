# Lead Pipeline AI

**An open-source prompt system that turns Claude (or any capable LLM) into a full B2B sales development team — prospecting, research, qualification, scoring, and personalized outreach — for any business, in any industry.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Made for Claude](https://img.shields.io/badge/built%20for-Claude-CC785C.svg)](https://claude.ai)
[![Status: Active](https://img.shields.io/badge/status-active-success.svg)](CHANGELOG.md)

---

## Why this exists

Every company eventually asks the same question: *"How do we get an AI to actually do sales development work — not just draft one email, but run the whole pipeline?"*

Most attempts fail for the same three reasons:

1. **The prompts are single-shot.** One giant "write me a cold email" prompt with no research behind it, no qualification logic, and no memory of what makes a lead worth pursuing.
2. **The context is missing.** An LLM without a tight, structured picture of your ICP, your value proposition, and your buyer will always default to generic marketing copy.
3. **The system isn't modular.** Swap one part (say, your outreach tone) and the whole thing breaks because everything was one monolithic prompt.

Lead Pipeline AI solves this by treating outbound sales the way an elite SDR/AE org would build it: as a **pipeline of discrete, composable stages**, each with its own prompt, its own inputs and outputs, and its own quality bar — all held together by a single, reusable **Company Context** file that every stage reads from.

This is not a SaaS product, not a wrapper, and not a chatbot demo. It is a documented, versioned **prompt engineering system** you clone, configure once for your business, and run inside Claude (Projects, Claude Code, the API, or Claude in a Cowork-style agent) — or adapt to any LLM tool that accepts system prompts and file context.

---

## What it does

Given a company (yours) and a target account or contact, Lead Pipeline AI can:

| Capability | Stage |
|---|---|
| Find and prioritize ideal prospects matching your ICP | `prospect-discovery.md` |
| Research a company's business model, market, and buying signals | `lead-research.md` |
| Identify and rank likely decision makers, champions, and blockers | `lead-research.md` |
| Score and qualify leads against Need, Budget, Authority, Timing | `qualification.md` |
| Write a personalized, non-generic cold email | `outreach-email.md` |
| Write LinkedIn connection requests and InMail | `linkedin.md` |
| Generate a 5-touch follow-up sequence with new value in every message | `followups.md` |
| Produce structured CRM notes and next-best-action | `crm.md` |
| Handle common objections with a proof-and-reframe structure | `objection-handling.md` |
| Prep for a discovery or demo call | `meeting-prep.md` |
| Draft a proposal or one-pager tailored to a specific buyer | `proposal.md` |

Every stage is a **standalone prompt**. You can use one in isolation ("just give me the lead score") or chain them into a full workflow ("research → qualify → write outreach → generate CRM notes") using the orchestration pattern documented in [`docs/workflow.md`](docs/workflow.md).

---

## Architecture

```
                         ┌─────────────────────────┐
                         │   company-context.md     │   ← you fill this out ONCE
                         │  (your ICP, offer, voice)│
                         └────────────┬─────────────┘
                                      │  read by every stage
                                      ▼
 ┌───────────────┐   ┌───────────────┐   ┌───────────────┐   ┌───────────────┐
 │  1. DISCOVERY  │──▶│  2. RESEARCH   │──▶│ 3. QUALIFY    │──▶│  4. OUTREACH   │
 │ find prospects │   │ company + DMs  │   │ score 1–10    │   │ email/LinkedIn │
 └───────────────┘   └───────────────┘   └───────────────┘   └───────┬───────┘
                                                                       │
                         ┌───────────────┐   ┌───────────────┐        │
                         │  6. CRM NOTES  │◀──│ 5. FOLLOW-UPS  │◀──────┘
                         │ + next action  │   │ 5-touch cadence│
                         └───────────────┘   └───────────────┘
```

Two design principles hold this together:

- **Single source of truth.** All context about *your* business lives in one file (`prompts/company-context-template.md`, filled in as `company-context.md`). Every downstream prompt is instructed to read it first. Change your positioning once — every stage updates.
- **Explicit contracts.** Every prompt file documents its exact inputs and outputs (see [`docs/prompt-guide.md`](docs/prompt-guide.md)). This is what makes the system modular: swap `outreach-email.md` for your own version and nothing else breaks, because the contract (inputs in, outputs out) is unchanged.

---

## Quick start

```bash
git clone https://github.com/<your-username>/Lead-Pipeline-AI.git
cd Lead-Pipeline-AI
```

1. **Fill out your Company Context.** Copy `templates/company-context-template.md` to `company-context.md` and fill it in — this takes 15–20 minutes and is the single highest-leverage step in the whole system. See [`docs/getting-started.md`](docs/getting-started.md).
2. **Load it into Claude.** Either:
   - Paste `company-context.md` + `prompts/system-prompt.md` into a new **Claude Project** (Project Knowledge), or
   - Point Claude Code / the API at this repo with `company-context.md` as a file in context, or
   - Attach both files to a Cowork session.
3. **Run a stage.** Paste the contents of any file in `/prompts` (e.g. `lead-research.md`) followed by your target company name. Claude will follow that prompt's instructions using your Company Context as background.
4. **Chain stages for a full workflow.** See [`docs/workflow.md`](docs/workflow.md) for the exact sequencing and how to carry outputs from one stage into the next.

Full setup instructions, including how to configure a Claude Project from scratch: [`docs/installation.md`](docs/installation.md).

---

## Example output

Input: `company-context.md` for a mid-market DevOps SaaS company + prospect "Acme Logistics, VP Engineering"

Output of `outreach-email.md` (abbreviated):

```
Subject: Acme's move to Kubernetes and your on-call load

Hi Priya,

Saw the engineering blog post about Acme's migration off ECS to EKS last month —
that's usually the point where on-call noise spikes 3-4x before it gets better.

We built [Product] for exactly that transition window: it cut alert-to-resolution
time by 40% for two other logistics-sector platforms mid-migration (Flexport,
ShipBob) without adding a new dashboard for your team to babysit.

Worth a 15-minute call next week to see if the timing lines up on your end?

[Name]
```

Notice: no "Hope you're doing well," no generic value prop, no invented facts — the prompt is instructed to cite only real, verifiable signals and flag anything it can't verify. See [`docs/prompt-guide.md`](docs/prompt-guide.md#personalization-rules) for the exact rules that produce this.

More full examples across six industries live in [`/examples`](examples/).

---

## Repository structure

```
Lead-Pipeline-AI/
├── README.md                    You are here
├── LICENSE                      MIT
├── CONTRIBUTING.md              How to add/improve prompts
├── CHANGELOG.md                 Version history
├── ROADMAP.md                   What's planned
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── docs/                        Every "how" and "why"
│   ├── getting-started.md
│   ├── installation.md
│   ├── configuration.md
│   ├── workflow.md
│   ├── prompt-guide.md
│   ├── best-practices.md
│   ├── customization.md
│   ├── examples.md
│   ├── faq.md
│   └── troubleshooting.md
├── prompts/                     The system itself — 12 modular, documented prompts
│   ├── system-prompt.md
│   ├── company-context-template.md
│   ├── lead-research.md
│   ├── prospect-discovery.md
│   ├── qualification.md
│   ├── outreach-email.md
│   ├── linkedin.md
│   ├── followups.md
│   ├── crm.md
│   ├── objection-handling.md
│   ├── meeting-prep.md
│   └── proposal.md
├── templates/                   Blank, fillable frameworks
│   ├── icp-template.md
│   ├── company-context-template.md
│   ├── buyer-persona-template.md
│   ├── outreach-framework.md
│   ├── discovery-questions.md
│   ├── lead-scoring-template.md
│   └── crm-template.md
├── examples/                    Fully worked examples, six industries
│   ├── saas/
│   ├── agencies/
│   ├── ai-startups/
│   ├── education/
│   ├── healthcare/
│   └── manufacturing/
├── workflows/                   Wiring this into real tools
│   ├── apollo-workflow.md
│   ├── clay-workflow.md
│   ├── instantly-workflow.md
│   ├── gmail-workflow.md
│   ├── notion-workflow.md
│   ├── hubspot-workflow.md
│   └── salesforce-workflow.md
└── .github/
    ├── ISSUE_TEMPLATE/
    └── PULL_REQUEST_TEMPLATE.md
```

---

## Customization

This system is deliberately business-agnostic. Nothing in `/prompts` hard-codes an industry, a tone, or a product. Everything specific to you lives in `company-context.md`. To adapt it:

- **Different tone/brand voice** → edit the "Brand Voice" section of your Company Context; every prompt inherits it.
- **Different qualification criteria (e.g. PLG vs. enterprise)** → edit `templates/lead-scoring-template.md`.
- **Add a new pipeline stage** (e.g. a pricing-negotiation prompt) → follow the contract format in [`docs/prompt-guide.md`](docs/prompt-guide.md) and drop it in `/prompts`.
- **Swap CRM/enrichment tools** → see `/workflows` for wiring patterns; the prompts themselves are tool-agnostic and only need structured data in, structured data out.

Full guide: [`docs/customization.md`](docs/customization.md).

---

## FAQ

**Does this require the Claude API / a paid plan?**
No. It works with Claude.ai (Projects), Claude Code, the API, or any LLM that accepts a system prompt and long context. See [`docs/faq.md`](docs/faq.md).

**Will this write "AI-sounding" emails?**
Only if your Company Context is thin. The system is designed so output quality is a direct function of input quality — see [`docs/best-practices.md`](docs/best-practices.md#avoiding-ai-sounding-outreach).

**Can I use this for outbound outside of B2B SaaS?**
Yes — see the Agencies, Education, Healthcare, and Manufacturing examples in `/examples`. The prompts are generic by design.

**Is this a replacement for a CRM or sequencing tool?**
No. It's the reasoning and writing layer. Pair it with your existing CRM/sequencer using the patterns in `/workflows`.

More: [`docs/faq.md`](docs/faq.md) · [`docs/troubleshooting.md`](docs/troubleshooting.md)

---

## Contributing

Contributions are welcome and encouraged — new prompt stages, new industry examples, new tool workflows, or improvements to existing prompts. Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening a PR; in short: every new or modified prompt must document its Purpose, Inputs, Outputs, Best Practices, Common Mistakes, and an Example, per the standard in [`docs/prompt-guide.md`](docs/prompt-guide.md).

## License

Released under the [MIT License](LICENSE). Use it, fork it, sell services built on top of it — just keep the license notice.

## Acknowledgments

Built for the open-source Claude and LLM-tooling community. If this saved your team time, a star helps other builders find it.
