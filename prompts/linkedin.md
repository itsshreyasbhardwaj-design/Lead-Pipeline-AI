# LinkedIn Outreach

## Purpose

Writes LinkedIn connection request notes and InMail/DM follow-ups — a distinct channel from email with its own constraints (300-character connection notes, different reading context, more casual register) and its own sequencing logic relative to email outreach.

## Inputs

- `company-context.md` (required)
- Research brief from `lead-research.md` (required)
- Which LinkedIn action is needed: connection request note, InMail, or a reply to prospect activity (comment/DM after they posted something)
- If reacting to prospect activity: the specific post/comment content

## Outputs

**Connection request note** (≤300 characters):
```
[One sentence: specific, genuine reason for connecting — never a pitch]
```

**InMail / first DM** (60–100 words, more casual than email):
```
[Opening tied to a specific signal]
[One-sentence bridge to relevance]
[Soft CTA — lower commitment than an email CTA, e.g. "worth a quick chat sometime?"
 rather than a specific meeting ask]
```

## Best Practices

- Never pitch in a connection request — the note's only job is to earn the accept. Reference something genuinely specific (a post, a shared connection, a shared group) with zero sales language.
- LinkedIn tone runs more casual than email by default — shorter sentences, less formal sign-off, no "Best regards."
- If reacting to a prospect's post, comment genuinely first (add real perspective, don't just praise it) before or instead of DMing — this is higher-trust than a cold DM and should be the preferred path when the signal exists.
- Sequence LinkedIn and email as complementary, not duplicate — see `docs/best-practices.md#multi-channel-sequencing` for suggested ordering.

## Common Mistakes

- Writing a connection note that's really just an email pitch compressed to 300 characters — recipients recognize and reject this pattern immediately.
- Using the exact same personalization angle and phrasing across email and LinkedIn to the same person — if both channels are used, vary the angle so it doesn't read as an obvious sequence.
- Sending an InMail with a hard, specific meeting ask ("Are you free Tuesday at 2pm?") before any rapport exists — save specific scheduling asks for after a reply or a warmer channel.

## When to Use

As a parallel or follow-up channel to `outreach-email.md`, particularly when a strong LinkedIn-native signal exists (a relevant post, a shared connection, group membership) that doesn't translate as well to email.

## Example

**Connection request:**
```
Hi [Name] — saw your post on Cargofy's Kubernetes migration, we work with a
few logistics platforms through similar transitions. Would love to connect.
```

**First DM (after connection accepted):**
```
Thanks for connecting. Curious how the K8s migration is going on the on-call
side — that's usually the roughest few weeks. We've helped a couple of teams
in a similar spot cut alert noise significantly during that window. Worth a
quick chat sometime if useful, no pressure either way.
```
