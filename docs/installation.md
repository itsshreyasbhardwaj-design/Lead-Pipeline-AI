# Installation

Lead Pipeline AI is a documentation and prompt library, not a piece of software — there is nothing to compile or run. "Installation" means getting the prompts loaded into whichever AI tool you'll use them with.

## Requirements

- Access to an LLM capable of following multi-step, structured instructions with long context — Claude (via claude.ai, Claude Code, or the API) is the reference target this system is documented against, but any comparably capable model works.
- A text editor to fill out `company-context.md`
- Optionally: accounts with the tools referenced in `/workflows` (Apollo, Clay, Instantly, Gmail, Notion, HubSpot, Salesforce) if you want to wire this into an existing sales stack

## Option A: Claude.ai Projects (no code, recommended for individuals and small teams)

1. Go to claude.ai and create a new Project.
2. Open Project Knowledge (or Project Settings → Knowledge) and upload:
   - `prompts/system-prompt.md`
   - Your filled-out `company-context.md`
3. Optionally upload any specific stage prompts you use most often (e.g. `prompts/outreach-email.md`) directly to Knowledge so you don't have to paste them each time — or keep them as copy-paste inputs per conversation, which keeps the project lighter.
4. Start a new chat inside the project. The system prompt and company context are now active background for every message in that project.

## Option B: Claude Code

Claude Code reads files directly from your working directory, which makes this repository's structure work natively:

```bash
git clone https://github.com/<your-username>/Lead-Pipeline-AI.git
cd Lead-Pipeline-AI
cp templates/company-context-template.md company-context.md
# fill out company-context.md
claude
```

Once inside a Claude Code session, reference prompts directly, e.g.:

> Read prompts/system-prompt.md and company-context.md, then follow prompts/lead-research.md for target company "Acme Corp"

## Option C: Claude API / Claude Agent SDK

Use `prompts/system-prompt.md` (with your company context appended or included as a second system block) as the `system` parameter, and pass the relevant stage prompt (e.g. `prompts/outreach-email.md`) plus your research brief as the user message. See Anthropic's API documentation at https://docs.claude.com for exact request formatting, and `docs/configuration.md` in this repo for how to structure multi-turn chained calls across pipeline stages.

## Option D: Any other LLM tool

Any tool that accepts a system prompt and supports long context (16K+ tokens recommended, given the combined length of the system prompt, company context, and a stage prompt) can run this system. Quality will vary by model capability, particularly around instruction-following on the accuracy/anti-hallucination rules — Claude models are the reference target for this repository.

## Verifying it's working

Run the sanity check in `docs/troubleshooting.md#sanity-check` — a short test prompt that confirms your system prompt and company context are both actually loaded and being followed.
