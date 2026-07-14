# Configuration

## The two required files

Every pipeline run needs exactly two files loaded as background context:

1. `prompts/system-prompt.md` — the fixed operating rules (accuracy, tone, output discipline). You should rarely need to edit this; if you do, see `docs/customization.md`.
2. `company-context.md` — your business-specific information, created from `templates/company-context-template.md`. This is the file you actively maintain.

Everything else in `/prompts` is a stage prompt you paste in on demand for the specific task at hand — these are not meant to be permanently loaded into a project's background context, since only one or two stages are typically relevant to any given moment in a workflow.

## Recommended Claude Project setup

```
Project Knowledge:
  ├── system-prompt.md        (from /prompts)
  └── company-context.md      (your filled-out file)

Per-conversation, paste in:
  └── whichever stage prompt is relevant (e.g. lead-research.md)
```

This keeps Project Knowledge lean (fast, cheap, always-relevant) while stage prompts stay flexible and swappable per task.

## Multi-user / team configuration

If multiple people on a team use this system:

- Maintain one canonical `company-context.md`, version-controlled in a private repo or shared drive, not copied ad hoc per person — inconsistent context produces inconsistent qualification and messaging.
- Assign an owner for `company-context.md` updates (typically a sales or marketing lead) and review it quarterly, per `docs/best-practices.md`.
- If different team members target different segments (e.g. SMB vs. enterprise), maintain segment-specific context files (`company-context-smb.md`, `company-context-enterprise.md`) rather than one file trying to cover both — mixed ICPs in one file weaken qualification precision for both segments.

## Configuring scoring weights

Default qualification scoring in `prompts/qualification.md` weights all seven dimensions (Need, Budget, Authority, Timing, Growth, Urgency, Overall ICP Fit) equally. To customize weights for your business (e.g. weighting Authority higher for an enterprise motion, or Timing higher for a seasonal business), edit `templates/lead-scoring-template.md` and reference your customized version explicitly when running `qualification.md`.

## Configuring output length and format

Every stage prompt specifies a default output length (e.g. outreach emails at 60–120 words). If your business norms differ (e.g. a market where longer, more formal emails perform better), state the override explicitly when you invoke the stage: "Follow prompts/outreach-email.md but target 150–180 words and a more formal register." Do not silently assume the model will adjust — be explicit.

## Environment variables and secrets (for tool integrations only)

The core prompt system requires no API keys or environment variables. If you wire this into the tool integrations documented in `/workflows` (Apollo, Clay, HubSpot, Salesforce, etc.), follow each workflow doc's guidance on secret handling — never commit API keys to this repository or any fork of it. See `SECURITY.md`.
