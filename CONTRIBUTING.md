# Contributing to Open Interview Network (OIN)

Thanks for helping. OIN is volunteer-run: every contribution of code, question cards, calibration clips, docs, or interviewer hours matters.

## Before you start

1. Read the [README](README.md) and [docs/INDEX.md](docs/INDEX.md).
2. Follow the [Code of Conduct](CODE_OF_CONDUCT.md).
3. Prefer small, reviewable changes. Phase 0 gates beat premature features.

## Developer Certificate of Origin (DCO)

We use a **DCO sign-off** instead of a CLA (unless dual-licensing is decided later).

Add this line to every commit message:

```
Signed-off-by: Your Name <your.email@example.com>
```

Git shortcut:

```bash
git commit -s -m "Short summary of why"
```

By signing off you certify that you have the right to submit the contribution under the project’s licences (see [LICENSE](LICENSE)).

## How to contribute

| Area | How |
| --- | --- |
| Bugs / spikes | Open an issue with steps, device, network (home / mobile / college Wi-Fi) |
| Docs | Edit files under `docs/`; keep assumptions labelled |
| Question cards | Follow [docs/product/question-card.md](docs/product/question-card.md); no leaked papers or confidential assessment content |
| Code (Phase 1+) | Fork → branch → PR; keep providers behind adapters; no secrets in the repo |
| Interviewer kits / calibration | Coordinate via Discussions before recording people |

### Good first issues

Look for labels `good-first-issue` and `phase-0`. Docs fixes and Interviewer Kit cards are especially welcome.

## Development principles

- **Humans are the product; software is scaffolding.**
- **No payment method** on any project cloud account you help administer.
- **Sensitive data stays on device** unless the member explicitly opts in.
- **Deterministic first, generative last** for scoring and coverage.
- **Adapters for every free provider** so swaps are configuration, not rewrites.
- **Accessibility is definition of done** (keyboard, screen reader, reduced motion, large text) — not polish later.
- Match existing style; do not drive-by reformat unrelated files.

## Pull requests

1. One concern per PR when practical.
2. Link the issue or Phase 0 spike it serves.
3. Update docs if behaviour or quotas change.
4. For anything touching auth, RLS, media, or consent: note the threat model in the PR description.
5. Do not commit `.env`, dumps, model binaries, or personal recordings.

## Local setup (placeholder)

Phase 0 uses short-lived spikes. A full `docker compose` “OIN in a box” local stack is planned for Phase 1–3. Until then:

- Document spike steps in the PR or a short note under `docs/` / issue comments.
- Prefer public, permissively licensed models; pin version + SHA-256 when adding a model reference.

## Content rules (question bank)

- No leaked exam papers or confidential recruiter assessments.
- No recruiter names in published notes.
- No copying from paid courses.
- Tag company **type** and round, not a specific confidential process.
- Licence contributions as **CC BY-SA 4.0** unless agreed otherwise.
- Every card needs 3–6 key points and a follow-up ladder (CI will enforce this later).

## Communication

- Default: GitHub Issues and Discussions.
- Be direct and kind. Assume good intent; escalate harassment per the Code of Conduct.
- Volunteer hours are capped by maintainers — say if you need to pause.

## Maintainers

Maintainer-led until outside contributors arrive; then an RFC process and `MAINTAINERS` file. Two admins must hold every critical account (see [docs/operations/account-checklist.md](docs/operations/account-checklist.md)).
