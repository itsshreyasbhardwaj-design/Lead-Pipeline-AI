# Customization

This system is deliberately generic at the prompt layer and specific at the context layer. Almost everything you'll want to change lives in `company-context.md`, not in `/prompts`. This guide covers what to customize and where.

## Changing tone and brand voice

Edit the Brand Voice section of `company-context.md`. Every prompt in `/prompts` is instructed to default to this section, so a single edit — e.g. changing "professional, consultative" to "casual, direct, no-fluff startup voice" — propagates to every stage without touching a single prompt file.

## Changing qualification criteria

Default scoring in `prompts/qualification.md` uses seven equally-weighted dimensions. Two ways to customize:

- **Reweight dimensions** — e.g. if Authority (reaching a real buyer) matters more than Growth trajectory for your motion, state the weighting explicitly when you invoke qualification, or maintain a custom version in `templates/lead-scoring-template.md`.
- **Add/remove dimensions** — e.g. a compliance-driven business might add a "Regulatory Trigger" dimension. Add it to your copy of the scoring template and reference it explicitly.

## Adding a new pipeline stage

Follow the seven-part structure in `docs/prompt-guide.md`: Purpose, Inputs, Outputs, Best Practices, Common Mistakes, When to Use, Example. Place the new file in `/prompts`, and add it to `docs/workflow.md`'s sequence diagram if it has a specific place in the pipeline order. See `CONTRIBUTING.md` for the contribution process if you intend to submit it upstream.

## Swapping out a stage

Because every stage has an explicit input/output contract (documented in its own file), you can replace any single prompt with your own version as long as the contract is preserved. For example, if you want a more aggressive/urgency-driven outreach style than `outreach-email.md` defaults to, write your own version that still expects a research brief as input and still outputs a single email with subject + body — nothing else in the pipeline needs to change.

## Industry-specific adaptation

Rather than modifying the generic prompts in `/prompts` for your industry, create an industry-specific Company Context and, if useful, an example file in `/examples` following the pattern of the six included industries. This keeps the core prompt library reusable for the whole community while letting your specific implementation be as tailored as you need.

## Multi-product or multi-segment businesses

If you sell multiple products to different segments, maintain separate Company Context files (`company-context-product-a.md`, `company-context-enterprise.md`, etc.) rather than merging them into one — a single file trying to describe two different ICPs and two different offers will weaken qualification and personalization precision for both. Load the relevant one per pipeline run.

## Programmatic orchestration

The prompts are structured with explicit input/output contracts specifically so they can be called programmatically, not just conversationally. To automate chaining (e.g. auto-run research → qualification → outreach for every new row in a spreadsheet), you would: parse each stage's Output structure as the schema for that stage's return value, feed it as Input to the next stage's API call, and persist intermediate outputs (especially the research brief and qualification score) for auditability. A reference implementation is planned — see `ROADMAP.md` — but is intentionally not bundled by default, to keep this repository a pure prompt/documentation library that works with any orchestration approach you choose (Claude API directly, a workflow tool like Zapier/Make, or a custom script).

## Localization

For non-English markets, translate `company-context.md` content and note formality/tone norms explicitly (e.g. many markets expect more formal register in first-touch outreach than US/UK norms default to). The structural prompts in `/prompts` are language-agnostic in instruction but currently written in English; translated variants are on the roadmap (`ROADMAP.md`) and contributions are welcome per `CONTRIBUTING.md`.
