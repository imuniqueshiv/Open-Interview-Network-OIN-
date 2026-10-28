# Security policy

## Supported versions

OIN is pre-release (Phase 0). Treat all builds as experimental until the Phase 1 closed alpha.

| Version | Supported |
| --- | --- |
| `main` (pre-1.0) | Best-effort |
| Tagged releases (when published) | Yes, until superseded |

## Reporting a vulnerability

**Do not open a public GitHub issue for security bugs.**

Email: `security@openinterview.network` (placeholder — replace with a private inbox or GitHub Security Advisories before public launch)

Include:

- Description and impact
- Steps to reproduce
- Affected commit / deployment if known
- Whether audio, auth, RLS, TURN credentials, or PII are involved

We aim to acknowledge within **72 hours** and to share a remediation plan when possible. Please give us a reasonable window before public disclosure.

## What we protect by design

- No default server storage of audio, video, resumes, or transcripts
- Row-level security on every table (Phase 1+)
- Secrets only in Edge Function / GitHub secrets — never in the repository
- Two admins + 2FA on every critical account
- Quota governor to degrade free tiers before abuse burns capacity
- Turnstile (or ALTCHA plan B) on sign-up

## Out of scope (product trust model)

- A peer capturing a call with their own device (code of conduct forbids it; we cannot technically prevent it)
- Compromised end-user devices
- Social engineering against volunteers

See [docs/privacy/data-protection.md](docs/privacy/data-protection.md) and [docs/trust-safety.md](docs/trust-safety.md).

## Incident expectations

- Public status page (Upptime) for availability incidents
- Breach runbook: notify affected users without delay; detailed report within 72 hours where required; CERT-In cyber-incident reporting within six hours of knowledge where applicable
- Post-incident note within one week for community-facing incidents
