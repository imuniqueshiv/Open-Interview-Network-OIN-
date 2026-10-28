# Scripts

Operational scripts (Phase 0–1 targets):

| Script (planned) | Purpose |
| --- | --- |
| `keepalive` | GitHub Action hitting Supabase health every 2 days |
| `backup` | Encrypted nightly DB dump → private repo |
| `restore-drill` | Timed restore into fresh project / local Postgres |
| `quota-report` | Snapshot free-tier counters for the weekly review |

Spikes for WebRTC / STT / avatar may be added under `scripts/spikes/` during Phase 0.
