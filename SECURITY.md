# Security Policy

## Reporting a Vulnerability

Lead Pipeline AI is a prompt/documentation repository — it does not ship executable services, so most traditional "vulnerabilities" don't apply. That said, please report any of the following privately rather than in a public issue:

- A workflow document that would cause credentials or API keys to be logged, committed, or exposed
- A prompt that could be used to exfiltrate data from a connected CRM/enrichment tool in an unintended way
- Any example file that accidentally contains real (non-fictional) personal data

**How to report:** open a private security advisory via GitHub's "Report a vulnerability" flow on this repository, or email the maintainer listed in the repository's GitHub profile. Do not open a public issue for security reports.

We aim to acknowledge reports within 5 business days.

## Data Handling Guidance for Users

This system is designed to process prospect and company data you supply. When using it:

- Never commit real prospect data, CRM exports, or API keys to a fork of this repository. `.gitignore` excludes common patterns (`company-context.md`, `*.csv`, `.env`) — extend it for your own workflow.
- Treat any enrichment/CRM API keys used in the `/workflows` integrations as secrets — use environment variables or your platform's secret manager, never hard-coded strings.
- Follow applicable data protection law (GDPR, CCPA, CAN-SPAM, PECR, etc.) for how you source, store, and contact leads. This project provides no legal advice and assumes no liability for how outputs are used — see the disclaimer in `docs/best-practices.md`.
