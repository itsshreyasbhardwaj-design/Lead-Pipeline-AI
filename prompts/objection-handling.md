# Objection Handling

## Purpose

Produces a reframe-and-respond script for a specific objection raised by a prospect, grounded in your actual proof points rather than generic sales-training language. Used both to prep before a call and to draft a written reply to an objection raised over email.

## Inputs

- `company-context.md` (required — specifically Objections We Hear Most Often and Social Proof)
- The specific objection as raised (verbatim if possible — tone and word choice matter)
- Context: is this written (email/chat reply) or verbal (talking points for a call)?

## Outputs

```
## Objection: "[verbatim or paraphrased objection]"

What's really being said: [the underlying concern, which is often not the literal words]

Reframe: [1-2 sentences repositioning the objection without dismissing it]

Evidence: [specific proof point from Company Context — a result, a case study,
a mechanism — never a generic reassurance]

Response draft: [full written reply if written context, or 3-4 talking-point
bullets if verbal]

Follow-up question to ask: [a question that moves the conversation forward
rather than ending on the objection]
```

## Best Practices

- Always acknowledge the objection as legitimate before reframing — "That's a fair concern" beats jumping straight to rebuttal, and reads as more consultative.
- Ground every reframe in a real proof point from Company Context (Social Proof, Unique Advantages) — an objection response with no evidence is just reassurance, which experienced buyers discount.
- End with a question, not a closing statement — objection handling should reopen dialogue, not try to "win" the exchange.
- For price/budget objections specifically, reframe toward cost of inaction (using the "What happens if this pain goes unsolved" field in Company Context) rather than discounting.

## Common Mistakes

- Treating the objection as a scripted checkpoint to overcome rather than genuine feedback — if the objection reveals a real gap (the product genuinely doesn't fit), say so rather than forcing a reframe.
- Responding only to the literal words of the objection instead of the underlying concern (e.g. "too expensive" is often really "I'm not yet convinced of the ROI") — the "What's really being said" step exists specifically to catch this.
- Using generic proof ("many customers see great results") instead of a specific, named or quantified result from Company Context.

## When to Use

Whenever a prospect raises a specific concern — during a call, in an email reply, or anticipated during meeting prep.

## Example

**Input objection:** "We already have an APM tool, not sure we need another dashboard."

**Output:**
```
What's really being said: Concern about tool sprawl and switching cost, not
necessarily doubt about the value of better observability.

Reframe: Totally fair — the goal isn't to replace your APM tool or add another
dashboard to check. [Product] sits on top of what you already have and reduces
what your team has to look at, not adds to it.

Evidence: For [named customer], we integrated directly with their existing
APM stack and cut time-to-resolution by 40% without them adding a new tool
to their on-call rotation — it consolidates signal, doesn't duplicate it.

Response draft: "Totally fair concern — and it's actually the opposite of
what we do. We plug into your existing APM setup and cut the noise your team
has to sift through, rather than adding another place to check. [Named
customer] saw a 40% drop in resolution time this way without changing their
core stack. Worth a 10-minute look at how the integration works?"

Follow-up question: "Which APM tool are you on today — is it [common tool],
or something else?"
```
