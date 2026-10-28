# Three ways to run OIN

| Mode | Who runs it | What it is | Why it matters |
| --- | --- | --- | --- |
| **Free hosted** | The project | Public instance on the free stack | Zero setup for students |
| **OIN in a box** | College / community | One `docker compose up`: self-hosted Supabase, web app, coturn, optional LiveKit, optional `oin-worker`, model mirror. Estimate: **4 vCPU / 8 GB RAM** | Data on campus; rooms 5–6; model files on LAN; capacity not limited by free quotas |
| **Local development** | Contributors | Same compose with fake media devices | Contribute without cloud accounts |

## Federation rules

- Each college that self-hosts is its own **data fiduciary** under DPDP for its members.
- Instances share the **public question bank** via git.
- Instances **never** share user data.
- Cross-college matching is out of scope until much later.

## Compose sketch (Phase 3 target)

Services (planned names):

- `web` — static / SSR-free app host  
- `supabase` (or postgres + gotrue + realtime stack)  
- `coturn`  
- `livekit` (optional profile)  
- `oin-worker` (optional profile)  
- `model-mirror` (optional)

Exact compose file arrives with Phase 3; Phase 0–1 may use hosted free tiers only.
