# Prompt Guide

This document is the specification every prompt in `/prompts` follows, and the standard any new or modified prompt must meet to be accepted via `CONTRIBUTING.md`.

## The seven-part structure

Every prompt file documents:

1. **Purpose** — what this stage does and why it's a separate stage rather than folded into another
2. **Inputs** — exact required and optional inputs, including which upstream files/outputs are assumed
3. **Outputs** — the exact structure the stage produces, so downstream stages and human readers know what to expect
4. **Best Practices** — concrete, stage-specific guidance (not generic advice)
5. **Common Mistakes** — specific failure modes, stated so the model (and human reviewers) can catch them
6. **When to Use** — where this stage sits in the overall `docs/workflow.md` sequence
7. **Example** — one realistic, fully worked input → output pair

This structure exists so that every stage is independently understandable and independently swappable. You should be able to read any single prompt file in isolation and know exactly what it needs and what it produces, without reading the rest of the repository.

## Personalization rules

Personalization is the highest-leverage and most failure-prone part of this system. Every outreach-facing stage (`outreach-email.md`, `linkedin.md`, `followups.md`) enforces:

- **Minimum three genuine, verifiable observations** about the prospect before writing outreach — pulled from `lead-research.md`, never invented. If fewer than three exist, the model should say so rather than pad with generic filler.
- **Source discipline** — every claim in a research brief is labeled Verified, Strong Inference, or Assumption (see `prompts/system-prompt.md`). Only Verified and clearly-labeled Strong Inference facts belong in outreach copy; Assumptions never appear as if fact.
- **The "swap test"** — before finalizing any outreach message, check whether it could be sent to a different company by only changing the name. If yes, it's not personalized enough.

## The accuracy contract

This system is built around a specific anti-hallucination contract, enforced in `prompts/system-prompt.md` and referenced by every research- and outreach-facing stage:

> Never fabricate facts about a company or person. Label every factual claim as Verified, Strong Inference, or Assumption. Never present an Assumption as fact. If information is missing, say so explicitly rather than guessing.

This contract is why the system produces research-grounded output rather than plausible-sounding fiction — and why it's safe to build real outreach on top of these outputs, provided the contract is actually followed. Spot-check outputs periodically against `docs/troubleshooting.md#verifying-accuracy`.

## Modifying a prompt

You can safely modify any stage prompt as long as you preserve its **input/output contract** — i.e., it still accepts what other stages expect to hand it, and still produces what other stages expect to consume. Example: you can rewrite `outreach-email.md`'s tone entirely for a more casual brand voice, as long as it still expects a research brief as input and still produces a single email with subject + body as output.

If you change a contract (e.g. you want `qualification.md` to output a 1–5 scale instead of 1–10), update every downstream stage that references it (`crm.md`, `meeting-prep.md`) and note the change in `CHANGELOG.md`.

## Writing a new stage

Follow `CONTRIBUTING.md`'s process. Use `prompts/lead-research.md` as the reference implementation for structure and depth — it's the most representative example of the level of specificity expected in Best Practices and Common Mistakes.
