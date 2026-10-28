# Roadmap

Assumes **2–4 part-time contributors**. If the team is smaller, slip dates — not gates. Each phase ends at a gate that can stop the project cheaply.

Source: proposal v1.1.2 (28 Oct 2026).

## Phase 0 — Validate (2–30 Nov 2026)

**Scope:** Free-stack spikes, avatar spike, in-browser STT benchmark, coverage scoring, 15 student interviews, licence/name decisions, one pilot college in talks.

**Gate to continue:**

- H8: ≥95% of test calls connect within 30 seconds (free TURN fallback)
- Drill report within 60 seconds on a mid-range phone
- STT good enough for scoring (assumed bar: WER ≤25% on Indian-English student audio)
- H1 and H3 pass
- Avatar meets spike thresholds **or** moved later
- ≥1 placement cell wants a pilot

Details: [docs/phase-0.md](docs/phase-0.md)

## Phase 1 — Core build (Dec 2026 – Feb 2027)

**Scope:** People-first room (audio, optional video, notes, timer, cards, rubric), matching & scheduling, rubric feedback, answer drills + Coach engine, sign-in, consent, basic moderation, comfort levels 1 & 4, status page, nightly backups. Closed alpha 20–30 students (Feb).

**Gate:** ≥95% alpha sessions connect; ≥15 human sessions with feedback; H7 (≥70% Coach/human agreement); one backup restored; no serious safety incident.

## Phase 2 — Pilot (Mar – May 2027)

**Scope:** 50–100 students at one college, weekly Mock Interview Nights, Interviewer Kits + certification with calibration clips, shared code editor, Hindi UI, full privacy notice live well before **13 May 2027** (DPDP operational duties).

**Gate:** Completion ≥70%, repeat ≥40%, no-show &lt;20%, institution contributing (interviewers / lab / node).

## Phase 3 — Comfort Mode & self-hosting (Jun – Aug 2027)

**Scope:** Avatar levels 2–3 if spike passed; scripted-adaptive AI interviewer; optional on-device LLM; GD rooms ≤4; cohort dashboard; community compute nodes; **OIN in a box** v1.

**Gate:** Median AI turn gap ≤4s on mid-range devices; ≥60% rate AI interviewer useful; Comfort Mode used by ≥30% of level 1–2 members; ≥1 college running its own copy.

## Phase 4 — Scale through federation (Sep – Dec 2027)

**Scope:** 5–10 colleges (public instance + self-hosts); rooms of 5–6 via optional nodes; Drive Mode; trust/reputation; AI-assisted human room; Hinglish if above accuracy bar.

**Gate:** ≥30% free-quota headroom at peak; colleges still active after a term.

## Phase 5 — Open models (2028)

**Scope:** Fine-tune small open-weight model or scoring classifier on consented de-identified data; dataset card; employer volunteer programmes; more cities.

**Gate:** Fine-tuned model beats baseline on held-out set.

## Explicitly cut / deferred

**From earlier versions (kept cut):** reputation economy & leaderboards until Phase 4; ATS-style resume scores (keep explainable gap list only); panel interviews; generative photoreal avatars / custom likeness uploads; native mobile apps; online aptitude tests; recruiter / job-board features.

**Cut in v1.1.2:** paid tiers & payments; hosted voice agents; rented GPUs; automated WhatsApp messaging; SMS sign-in; managed media services as critical path.

## Near-term focus

Right now: execute [docs/phase-0.md](docs/phase-0.md) and land the six decisions in [docs/decisions.md](docs/decisions.md).
