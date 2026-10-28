# Reliability engineering

## Targets (assumptions — replace after pilot)

| Target | Phase 1 | Phase 3 |
| --- | --- | --- |
| Connect within 30s | ≥95% | ≥98% |
| Sessions drop before end | &lt;5% | &lt;5% |
| Drill report after last answer | ≤60s mid-range phone | ≤60s |
| Monthly site availability (Upptime) | ≥99% measured — **no SLA promise** | ≥99% |

## Mechanisms

1. **Adapters** for every provider (signaling, TURN, SMTP, model host).
2. **Quota governor** — Postgres counters for TURN, email, Lane 3. Alerts at 70% / 90%. At limit: direct-only connections, push/Telegram instead of email, Lane 3 off.
3. **Keep database awake** — real term-time traffic + scheduled call every **2 days** from GitHub Actions (free projects pause after a week idle). Wake runbook one page; backups mandatory.
4. **Offline-first PWA + static mirror** — shell + question bank without server; GitHub Pages serves same build if main host fails.
5. **Backups & restore drills** — nightly encrypted dump to private repo; monthly restore to fresh project/local Postgres (target: back up and running ≤2 hours — assumption).
6. **Synthetic checks** — Upptime on site, DB health, `ice-servers`; scheduled Playwright with two Chromium + fake media.
7. **Release discipline** — feature flags in DB, staged rollout, one-click Pages rollback.
8. **Quarterly chaos drills** — block TURN, pause DB, kill signaling; verify degraded modes.
9. **Device/network matrix** — 2 low-end + 1 mid-range Android, lab PC; home / mobile / college Wi-Fi every release.
10. **Incident process** — one-page runbook, public status page, post-incident note within a week.
