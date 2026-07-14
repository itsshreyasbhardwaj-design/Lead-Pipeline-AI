# Best Practices

## Building an ICP that actually sharpens output

A weak ICP ("mid-market SaaS companies") produces weak qualification and generic outreach, because the model has nothing specific to reason against. A strong ICP is built from real won-deal patterns: pull your last 10–20 closed-won deals and look for what they actually had in common — company size band, a specific trigger event, a specific buyer title, a specific pain point they described in their own words. Encode that pattern into `company-context.md`, not a hypothetical persona.

## Researching prospects rigorously

Treat every research brief as something that has to survive a fact-check. A signal is only a signal if it's time-bound and specific — a funding round, a job posting, a product launch, a leadership change, a stated public initiative. Generic company facts (industry, size, "growing company") are context, not signals, and shouldn't be treated as personalization material. Always note what couldn't be verified rather than letting a gap quietly disappear.

## Writing personalized outreach that doesn't sound like AI

The single biggest driver of "AI-sounding" outreach isn't word choice — it's genericness. An email is recognizable as mass-produced the moment it could be sent to a different company by swapping the name. The fix isn't better sentences; it's better research. Before writing any outreach, confirm you have at least three real, verifiable, specific observations about the prospect. If you don't, get more research before writing, rather than writing around the gap with generic value-prop language.

Secondary drivers worth eliminating: banned filler phrases ("hope you're doing well," "just following up"), multiple CTAs in one message, and feature-listing instead of problem-first framing. All three are addressed directly in `prompts/system-prompt.md` and `prompts/outreach-email.md`.

## Lead qualification discipline

Score every dimension of `prompts/qualification.md` independently before computing a composite. The most common qualification error is anchoring on one strong signal (e.g. "they just raised funding!") and inflating every other dimension to match a gut feeling. A structured, dimension-by-dimension score catches "good fit, bad access" situations (great Need, terrible Authority) that a holistic gut score would average away into a misleadingly medium number.

Recalibrate your "Pursue Now" threshold against actual outcomes once you have enough closed deals to look back on — the default thresholds in this system are reasonable starting points, not empirically tuned for your specific business until you have that data.

## Sales psychology in practice

People respond to messages that make them feel understood, not sold to. The mechanism behind good personalization isn't flattery — it's specificity, because specificity is the only signal a busy person can use to distinguish "this person did real work to understand my situation" from "this is a template." Every stage in this system optimizes for that signal: real research feeding real personalization feeding a message that reads as understanding rather than pitching.

Reciprocity matters in follow-up sequences specifically — a follow-up that offers something (a relevant resource, a specific insight, an introduction) outperforms one that only asks. See `prompts/followups.md` for the structure this enforces.

## Personalization frameworks

A reliable personalization hierarchy, roughly in order of strength: (1) something the prospect personally said or wrote (a post, a talk, an interview quote) — most specific to them as an individual, (2) a company-specific, recent, verifiable event (funding, launch, hire, migration) — specific to their situation, (3) an industry-wide trend with a specific tie to their likely position — weaker but still usable if 1 and 2 aren't available, (4) generic company facts (size, industry) — not personalization on their own, use only as supporting context, never as the hook.

## Follow-up timing

Irregular spacing reads as more human than a rigid weekly cadence — see the timing guidance in `prompts/followups.md`. As a general default: first follow-up at 3–4 days, then roughly weekly with slight variation, tapering to a final "breakup" message around day 28–30. Adjust based on your sales cycle length — a fast-moving PLG motion may compress this to two weeks total; an enterprise motion may stretch it to 6–8 weeks.

## Multi-channel sequencing

Email and LinkedIn work best as complementary, not duplicate, touches. A common effective pattern: Day 0 email + same-day LinkedIn connection request (low-commitment, different register) → Day 3–4 follow-up email → LinkedIn comment on any relevant prospect activity if it occurs → Day 7–8 follow-up email with new value → etc. Never send the identical message/angle on both channels to the same person in the same week — it reads as automated when a prospect sees both.

## CRM organization and pipeline management

Keep CRM notes (`prompts/crm.md`) as an append-only interaction log, not a single overwritten snapshot — the history is what makes handoffs and re-qualification decisions defensible. Every note should end in a specific, dated, ownable Next Best Action; a pipeline where notes don't produce clear next actions tends to stall regardless of lead quality. Move a deal's stage only on verified buyer behavior (a meeting held, a next step confirmed by them, not just by you) — optimistic stage-setting is one of the most common causes of inaccurate forecasting.

## A disclaimer on compliance

This system helps you write and prioritize outreach; it does not provide legal advice. You are responsible for complying with applicable law in your jurisdiction and your prospects' jurisdictions — including CAN-SPAM, GDPR, CCPA/CPRA, PECR, and any platform-specific terms of service (e.g. LinkedIn's outreach policies). Build consent, opt-out handling, and data retention practices into your actual sending workflow; none of that is handled by the prompts in this repository.
