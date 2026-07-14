# FAQ

**Does this require the Claude API or a paid plan?**
No. It works with the free or paid tiers of claude.ai (Projects), Claude Code, the API, or any other LLM tool that accepts a system prompt and supports enough context length to hold the system prompt, your company context, and a stage prompt at once (16K+ tokens recommended).

**Will this write outreach that sounds like AI?**
Output quality is a direct function of input quality. If your `company-context.md` is thin (generic ICP, no real proof points), outputs will trend generic regardless of the prompt engineering underneath. See `docs/best-practices.md#writing-personalized-outreach-that-doesnt-sound-like-ai`.

**Can I use this outside B2B SaaS?**
Yes. The prompts in `/prompts` are deliberately industry-agnostic; all business-specific detail lives in `company-context.md`. See `/examples` for worked examples in agencies, AI startups, education, healthcare, and manufacturing, in addition to SaaS.

**Is this a CRM or sequencing tool replacement?**
No. It's the reasoning and writing layer — research, qualification, and copy generation. It's designed to be paired with your existing CRM and sequencing tool via the integration patterns in `/workflows`, not to replace them.

**How is this different from just asking ChatGPT/Claude to "write me a sales email"?**
A single-shot prompt has no structured research step, no qualification gate, and no persistent context about your business — so it defaults to generic value-prop language. This system separates research, qualification, and writing into distinct, verifiable stages, each with an explicit accuracy contract (see `docs/prompt-guide.md#the-accuracy-contract`), and holds your business context in one reusable file instead of re-explaining it every time.

**Does this scrape data or connect to LinkedIn/Apollo/etc. automatically?**
No. This repository contains prompts and documentation only — no scraping code, no automated data collection. `/workflows` documents how to manually or semi-automatically wire this into tools you already use and have proper access/licensing for; you are responsible for complying with each tool's terms of service.

**How do I know if a lead score is actually accurate for my business?**
The default scoring model in `prompts/qualification.md` is a reasonable starting framework, not empirically tuned to your specific win patterns. Recalibrate your "Pursue Now" threshold once you have enough closed-won/closed-lost data to compare scores against actual outcomes — see `docs/best-practices.md#lead-qualification-discipline`.

**Can multiple people on my team use this consistently?**
Yes — maintain one canonical, version-controlled `company-context.md` per team/segment rather than letting each person maintain their own. See `docs/configuration.md#multi-user--team-configuration`.

**What if my business sells to multiple very different segments?**
Maintain separate Company Context files per segment rather than one file trying to cover both — see `docs/customization.md#multi-product-or-multi-segment-businesses`.

**Is there a hosted version of this?**
No, and there are no plans for one — see the Non-goals section of `ROADMAP.md`. This stays a prompt and documentation library you run inside tools you already use.

**How do I contribute a new industry example or tool workflow?**
See `CONTRIBUTING.md` for the full process and quality bar.
