# Free stack and plan B

Licences below are **expected** from public repos — confirm when pinning versions.

| Layer | Choice | Licence | Free allowance relied on | Plan B |
| --- | --- | --- | --- | --- |
| Web app | Next.js (static export), TypeScript, Tailwind, PWA | MIT | None | Vite + React or SvelteKit |
| Static hosting | Cloudflare Pages, mirrored on GitHub Pages | n/a | Unlimited static requests; Pages ~500 builds/month | GitHub Pages or college nginx |
| DB / auth / realtime | Supabase (Postgres + RLS, Auth, Realtime, Edge Functions); SQL migrations | Apache-2.0 / PostgreSQL | Free: 2 projects, 500 MB DB, 1 GB files, 5 GB egress, 50k MAU, 200 concurrent realtime; **pauses after ~1 week idle** | Self-host Supabase Docker; or Postgres + small WS server |
| Signaling | Supabase Realtime private channels behind `SignalingTransport` | n/a | Realtime quota (~2M messages / 200 connections — verify) | Cloudflare Durable Objects (SQLite-backed free limits) or Node `ws` in self-host |
| Media | Browser WebRTC: Opus, optional video, data channels | Open standard | None | Paste-a-meeting-link (product degraded mode) |
| STUN / TURN | Cloudflare STUN + Realtime TURN | n/a | First 1,000 GB/month TURN+SFU egress free, no card (verify) | coturn or LiveKit TURN on free VM / college |
| Rooms &gt;4 (optional) | Self-hosted LiveKit | Apache-2.0 | Free VM / college | Cap rooms at 4 |
| Shared notes / code | Yjs over peer; Monaco; Pyodide | MIT / MIT / MPL-2.0 | None | Plain shared text |
| On-device AI | Transformers.js + ONNX Runtime Web; optional WebLLM | Apache-2.0 | None | Typed answers + rule feedback |
| Avatar | MediaPipe Face Landmarker, three.js, three-vrm | Apache-2.0 / MIT / MIT | None | Levels 1 and 4 only |
| Email | Brevo free SMTP as Supabase custom SMTP | n/a | 300 emails/day; branding on free plan | Resend free; lean on push/Telegram |
| Push / chat reminders | Web Push (VAPID), Telegram bot | Open / free API | None | Email |
| Bot protection | Cloudflare Turnstile | n/a | Free unlimited challenges (verify widget limits) | ALTCHA self-hosted |
| CI / releases | GitHub Actions (public repo) | n/a | Free standard runners for public repos | Self-hosted runner |
| Status / uptime | Upptime (Actions + Pages) | MIT (confirm) | Public repo | Uptime Kuma on free VM |
| Analytics / errors | First-party aggregates + sampled errors in Postgres | n/a | Inside DB quota | — |
| Backups | Nightly encrypted dump (age) → private GitHub repo | age (BSD) | Private repos | Download to college machine |
| Docs / community | GitHub Discussions + Pages docs | n/a | Free | Any static host |

## Picture

```
Learner browser (PWA)                              Free cloud
┌─────────────────────────────────┐               ┌────────────────────────────┐
│ UI + service worker             │── static ──▶  │ Cloudflare Pages           │
│ Coach engine (JS / Wasm)        │               │ (+ GitHub Pages mirror)    │
│ On-device speech / optional LLM │               └────────────────────────────┘
│ Avatar: MediaPipe + three.js    │── HTTPS/WSS ▶ ┌────────────────────────────┐
│ WebRTC ◀── media / data ────────┼──▶ Partner    │ Supabase Auth, Postgres RLS│
└──────────────┬──────────────────┘               │ Realtime, Edge Functions   │
               │ relay only if needed             └────────────────────────────┘
               ▼
      Cloudflare STUN / TURN          Plan B: coturn on college / free VM

Optional (never critical path):
  college / free VM → LiveKit (5–6), oin-worker, coturn, model mirror
GitHub: code, CI, Upptime, encrypted nightly backups
```

Confirm current free-tier pages before relying on numbers (free tiers change; Cloudflare D1 daily limits began enforcement 1 Sep 2026 as a reminder that limits get real).
