# Getting Started

This guide gets you from a fresh clone to your first real research brief and outreach email in under 30 minutes.

## Step 1 — Clone the repository

```bash
git clone https://github.com/<your-username>/Lead-Pipeline-AI.git
cd Lead-Pipeline-AI
```

## Step 2 — Fill out your Company Context (15–20 minutes)

Copy the template:

```bash
cp templates/company-context-template.md company-context.md
```

Open `company-context.md` and fill out every section honestly and specifically. This is the highest-leverage 20 minutes you'll spend on this system — every prompt in `/prompts` reads this file, so vague input here produces generic output everywhere downstream.

If you're not sure how detailed to be, look at any filled-out example in `/examples` for the level of specificity to aim for.

`company-context.md` is gitignored by default — it contains your real business information and should not be committed to a public fork unless you intend it to be public.

## Step 3 — Load it into your tool of choice

Pick one:

**Claude.ai (Projects) — recommended for most people**
1. Create a new Project
2. Add `prompts/system-prompt.md` and your `company-context.md` to Project Knowledge
3. Start a conversation in the project — you're ready to run any stage

**Claude Code / API**
Pass `prompts/system-prompt.md` as your system prompt and include `company-context.md` as a file in context on every call. See `docs/installation.md` for exact setup.

**Any other LLM tool that accepts a system prompt + long context**
The same two files (system prompt + company context) work anywhere that supports persistent context — the prompts themselves are model-agnostic.

## Step 4 — Run your first stage

If you already know who you want to target, start with research:

> Paste the full contents of `prompts/lead-research.md`, then add: "Target company: [Company Name]"

If you need to find targets first:

> Paste the full contents of `prompts/prospect-discovery.md`, then describe your sourcing pool (a list of companies, a market segment, an export from a tool)

## Step 5 — Chain into a full workflow

Once you're comfortable running individual stages, see `docs/workflow.md` for how to chain discovery → research → qualification → outreach → follow-ups → CRM notes into one continuous pipeline run per lead.

## What good output looks like

Compare your first output against the examples in `docs/examples.md` and `/examples`. If your output feels generic, the almost-certain cause is a thin Company Context — go back and add more specificity, especially to Ideal Customer Profile and What We Solve.

## Next steps

- Read `docs/prompt-guide.md` to understand exactly how each stage is structured and how to modify one
- Read `docs/best-practices.md` before sending your first real outreach
- If you hit an unexpected result, check `docs/troubleshooting.md` first
