# Open Interview Network (OIN)

**A free, open-source practice network where real people interview you against a fair rubric — and software on your own device covers the gaps.**

> Promise: a real interview with a real person within **48 hours** of signing up, and a clear list of what to fix next — **free forever**.

This repository is the starting home for OIN (proposal **v1.1.2**, 28 Oct 2026). Product code lands in phases; **Phase 0** validates the free stack and the idea before a full build.

---

## Why OIN exists

Interview skill is learned by doing. Students who most need practice often have the least access: busy seniors, few mentors, camera anxiety, and paid tools that lock rich feedback behind a paywall.

AI-only mock interview products are crowded. OIN competes on what is hard to copy and cheap to give:

- Trained **human** interviewers (reciprocity: everyone is candidate and interviewer)
- A **public rubric** with evidence-linked scores
- Cohort tools every college gets **free**
- A privacy-first **comfort ladder** (voice → avatar → video)
- **Open source** with self-hosting (“OIN in a box”)

Sensitive work (drills, speech-to-text, scoring, optional AI interviewer) runs **on the learner’s device**. Human sessions travel **browser to browser**. That is how “free for everyone” stays survivable.

---

## Zero-cost rule

1. **No fixed cost and no per-use cost** in the core loop — no card, paid plan, or paid API key required.
2. **Everything we ship is open source** — AGPL-3.0 (app), Apache-2.0 / MIT (libraries), CC BY-SA 4.0 (content).
3. A free cloud service is allowed only if signup needs **no card**, a **plan B** exists, and a **quota guard** stops us crossing its limit.
4. The core loop is a **human practising with a human** — it must survive losing any one free provider.
5. Anything that cannot be free is optional or has a free route (see [docs/operations/cost-model.md](docs/operations/cost-model.md)).

---

## Status

| Phase | Window | Status |
| --- | --- | --- |
| **0 — Validate** | 2–30 Nov 2026 | **Current** — spikes, interviews, pilot talks |
| 1 — Core build | Dec 2026 – Feb 2027 | Not started |
| 2 — Pilot | Mar – May 2027 | Not started |
| 3 — Comfort Mode + self-host | Jun – Aug 2027 | Not started |
| 4 — Federation | Sep – Dec 2027 | Not started |
| 5 — Open models | 2028 | Not started |

See [ROADMAP.md](ROADMAP.md) and [docs/phase-0.md](docs/phase-0.md).

---

## Docs map

| Doc | What it covers |
| --- | --- |
| [docs/INDEX.md](docs/INDEX.md) | Full documentation index |
| [docs/vision.md](docs/vision.md) | Problem, positioning, who we serve |
| [docs/product/](docs/product/) | Core loop, modes, comfort ladder, kits, rubric |
| [docs/architecture/](docs/architecture/) | Free stack, realtime, data model, capacity |
| [docs/ai/](docs/ai/) | On-device Coach, model lanes, licences |
| [docs/privacy/](docs/privacy/) | DPDP, data handling, consent outline |
| [docs/operations/](docs/operations/) | Accounts, quotas, provider playbook, cost |
| [docs/trust-safety.md](docs/trust-safety.md) | Moderation, harassment, scams |
| [docs/growth.md](docs/growth.md) | Loops, channels, pilot funnel |
| [docs/proposals/v1.1.2.md](docs/proposals/v1.1.2.md) | Full proposal snapshot |

---

## Stack (high level)

| Layer | Choice | Plan B |
| --- | --- | --- |
| Web app | Next.js static export + PWA | Vite / SvelteKit static |
| Hosting | Cloudflare Pages (+ GitHub Pages mirror) | College nginx |
| DB / auth / realtime | Supabase free (Postgres + RLS) | Self-host Supabase / Docker |
| Media | Browser WebRTC (mesh ≤4) | Paste-a-meeting-link degraded mode |
| STUN / TURN | Cloudflare free TURN | coturn on college / free VM |
| AI drills | On-device Coach + Whisper/Vosk class | Typed answers + rules only |
| Email | Brevo free SMTP | Resend free / push / Telegram |
| CI / status / backups | GitHub Actions, Upptime, encrypted dumps | Self-hosted runner |

Architecture diagram and quotas: [docs/architecture/stack.md](docs/architecture/stack.md).

---

## Repository layout

```
oin/
├── README.md
├── LICENSE                 # AGPL-3.0
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── SECURITY.md
├── ROADMAP.md
├── docs/                   # Product & ops documentation
├── apps/                   # (Phase 1+) web app and related apps
├── packages/               # (Phase 1+) shared libs (Coach, rubric, adapters)
└── scripts/                # Keepalive, backups, restore drills
```

Application code is intentionally thin until Phase 0 gates pass.

---

## Quick start (contributors)

Phase 0 is spikes and validation — there is no installable product yet.

1. Read [docs/vision.md](docs/vision.md) and [docs/phase-0.md](docs/phase-0.md).
2. Read [CONTRIBUTING.md](CONTRIBUTING.md) (DCO sign-off).
3. Pick a Phase 0 spike or doc issue labelled `good-first-issue` when available.
4. Never attach a payment method to any project account.

When “OIN in a box” ships (Phase 3), a college will run roughly:

```bash
docker compose up
```

(estimated ~4 vCPU / 8 GB RAM — see [docs/architecture/deployment-modes.md](docs/architecture/deployment-modes.md)).

---

## Licensing

| Asset | Licence |
| --- | --- |
| Application | [AGPL-3.0](LICENSE) |
| Reusable libraries (planned) | Apache-2.0 |
| Question cards & content | CC BY-SA 4.0 |
| Model weights / datasets | Explicit per-artefact licence |

Confirm dependency licences when versions are pinned (Phase 0, week 3).

---

## Privacy in one line

Audio, video, resumes, and transcripts stay on the learner’s device by default. OIN does not record sessions. Scores sync only with opt-in. See [docs/privacy/](docs/privacy/).

---

## Community & support

- **Discussions:** GitHub Discussions (once the org repo is public)
- **Conduct:** [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)
- **Security reports:** [SECURITY.md](SECURITY.md)
- **Grievance contact:** TBD before public pilot (required under DPDP design)

---

## Decisions still owned by the project lead

Six decisions only the product lead can make (see [docs/decisions.md](docs/decisions.md)):

1. Final licence confirmation  
2. Distinctive public name (search trademarks first)  
3. Launch **18+** only  
4. First pilot college  
5. Comfort Mode in pilot vs deferred after avatar spike  
6. Accept v1.1.2 trade-offs (no paid tier, capacity ceiling, groups of ≤4 on free path)

---

## Disclaimer

This is not legal or financial advice. Free tiers change; every free service is treated as replaceable. Planning numbers in the docs are labelled as assumptions until measured.
