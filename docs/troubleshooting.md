# Troubleshooting

## Sanity check

Before relying on any real output, confirm both required files are actually loaded and being followed:

> "Confirm you have loaded the system prompt and my company context. Summarize my Ideal Customer Profile back to me in one sentence, and confirm you understand the accuracy rules around Verified/Inferred/Assumed facts."

If the model can't accurately summarize your ICP, `company-context.md` isn't loaded correctly — recheck Project Knowledge / your context-loading method.

## "The output feels generic"

This is almost always a thin Company Context, not a prompt problem. Specifically check:

- Is your Ideal Customer Profile specific (size band, geography, buyer titles, buying triggers) or just an industry name?
- Does "What We Solve" list real, specific pain points, or generic ones ("increase efficiency")?
- Does "Social Proof" have real, specific proof points, or nothing at all?

Compare your file against `/examples` for the target level of specificity. See also `docs/best-practices.md#writing-personalized-outreach-that-doesnt-sound-like-ai`.

## "It's inventing facts about a prospect"

This should not happen if `prompts/system-prompt.md` is properly loaded — its accuracy rules explicitly require labeling every claim as Verified/Strong Inference/Assumption and forbid presenting assumptions as fact. If you observe fabrication:

1. Re-run the sanity check above to confirm the system prompt is actually active.
2. Explicitly remind the model mid-conversation: "Re-check every factual claim in your last output — label each as Verified, Strong Inference, or Assumption, and flag anything that isn't clearly Verified."
3. If it persists, the underlying model may not be reliably following complex system instructions — this system is documented against Claude models specifically because of their instruction-following reliability on exactly this kind of constraint; results may vary with other models.

## Verifying accuracy

Periodically spot-check research briefs against primary sources yourself, especially for high-stakes/high-value accounts — treat AI-generated research as a strong first draft that accelerates your work, not as a substitute for a final human sanity check before it drives real outreach or a proposal.

## "Qualification scores don't match my gut feel"

First, check whether your gut feel is anchored on one strong signal (see `docs/best-practices.md#lead-qualification-discipline` on this common bias) — the structured score may be correctly catching a weakness (e.g. Authority) that a holistic gut read glossed over. If, after enough closed deals, the scores genuinely don't correlate with real outcomes, recalibrate your thresholds and dimension weights per `docs/configuration.md#configuring-scoring-weights`.

## "Follow-ups feel repetitive"

Check that each follow-up in the sequence is genuinely introducing new value/angle, not just rephrasing "checking in" — this is the most common quality regression in `prompts/followups.md` output. Explicitly instruct: "Make sure each of the five follow-ups uses a completely distinct angle — list the angle used for each one before writing it."

## "The model won't proceed without more information"

This is by design, not a bug — see the accuracy contract in `docs/prompt-guide.md`. If you deliberately want to proceed with limited information (e.g. early-stage discovery with minimal public data), say so explicitly: "Proceed with what's available, and clearly flag every assumption you have to make."

## Context length issues

If you're combining a long system prompt, a long company context, and a long stage prompt and hitting context limits, trim your Company Context to the essentials for the task at hand, or split very long Ideal Customer Profile / Social Proof sections into a shorter primary version with a longer reference version you paste in only when needed.

## Still stuck?

Open an issue on the repository describing the specific output you got, the stage prompt used, and what you expected instead — see `CONTRIBUTING.md` for issue guidelines.
