# Contributing to Lead Pipeline AI

Thanks for considering a contribution. This project's value comes entirely from the quality and rigor of its prompts, docs, and examples — so the bar for merging is "would a professional GTM/sales operator trust this in production," not "does it technically work."

## Ways to contribute

- **New pipeline stage** — a new prompt for a step the system doesn't cover yet (e.g. renewal outreach, channel-partner outreach, event follow-up).
- **Improve an existing prompt** — sharper instructions, better failure-mode handling, clearer output contract.
- **New industry example** — a fully worked example in `/examples` for a vertical not yet covered.
- **New tool workflow** — wiring instructions for a CRM, enrichment tool, or sequencer not yet in `/workflows`.
- **Documentation** — fixing unclear instructions, adding a missing FAQ, improving `docs/troubleshooting.md`.

## Before you start

Open an issue first for anything beyond a small fix (typo, broken link) using the **New Prompt/Workflow Proposal** issue template. This avoids duplicate work and lets a maintainer flag scope issues early.

## Standards for a new or modified prompt

Every prompt file in `/prompts` must include, in this order (see `docs/prompt-guide.md` for the full spec and `prompts/lead-research.md` as a reference implementation):

1. **Purpose** — one paragraph, what this prompt does and why it exists as a separate stage
2. **Inputs** — the exact variables/files the prompt expects (e.g. "Company Context file, target company name")
3. **Outputs** — the exact structure of what it produces
4. **Best Practices** — 3–6 concrete do's specific to this stage
5. **Common Mistakes** — 3–6 concrete failure modes and how the prompt guards against them
6. **When to Use** — one or two sentences on the right moment in the pipeline to run this
7. **Example** — one realistic, fully worked input → output pair (fictional company, clearly labeled)

Prompts must be **business-agnostic**. If a prompt only makes sense for one industry, it belongs in `/examples`, not `/prompts`.

Prompts must be **modular**. A prompt in `/prompts` cannot assume another specific prompt already ran, beyond consuming `company-context.md` and clearly-named prior-stage outputs. State this explicitly in Inputs.

## Standards for a new example

Each folder in `/examples/<industry>/` should contain one `example.md` with:

- A realistic (fictional) filled-out Company Context for that industry
- A realistic (fictional) target prospect
- Full outputs for at least: lead research, qualification score, one outreach email, one LinkedIn message

Never include real people's names, real private company data, or scraped personal information. Fictional composites only.

## Standards for a new workflow doc

Each `/workflows/<tool>-workflow.md` should cover: what the tool is for in this pipeline, the data handoff points (what goes in, what comes out), a concrete step-by-step setup, and a note on API/rate-limit or plan-tier gotchas. Do not include real API keys or account-specific screenshots.

## Style

- Write in the second person, direct and instructional — this is documentation, not marketing copy.
- No filler, no "in today's competitive landscape" throat-clearing.
- Use tables for anything comparative or structured; prose for explanation.
- Markdown only. No embedded HTML unless there's no other way to express it.

## Pull request process

1. Fork, branch (`feature/<short-description>`), commit with clear messages.
2. Fill out `.github/PULL_REQUEST_TEMPLATE.md` completely — incomplete PRs will be asked to update before review.
3. One maintainer review is required before merge. Expect feedback on prompt rigor, not just correctness.
4. Add an entry to `CHANGELOG.md` under `[Unreleased]`.

## Code of Conduct

Participation in this project is governed by [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).
