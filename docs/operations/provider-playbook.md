# Provider-change playbook

| Provider | What could change | Early warning | Plan B | Effort (assumption) |
| --- | --- | --- | --- | --- |
| Supabase free | Pause rule, project limits, connection caps, pricing | Pricing page, email, quota alerts | Self-host same stack; restore nightly backup | 1–2 days |
| Cloudflare Pages / Workers / TURN | Limit enforcement; TURN free tier | Changelog, usage dashboard | GitHub Pages; coturn | Hours |
| Oracle free VM (optional) | Idle reclamation (third-party reports exist — check Oracle terms) | Reclamation emails | Rebuild from compose on any server | &lt;1 hour once scripted |
| Brevo | Daily limit, branding, terms | Dashboard | Resend free, or push/Telegram only | Hours |
| Hugging Face | Rate limits or terms | Failed downloads in error reports | College node mirror | Hours |
| GitHub | Pages or Actions policy | Notices | Other static host; self-hosted runner | Hours |
| Turnstile | Terms | Notices | ALTCHA | ~1 day |
| Browser vendors | WebGPU / speech API behaviour | Test matrix, release notes | Capability checks + STT fallbacks | Ongoing |

## Order when a free service breaks

1. Degrade gracefully (quota governor)  
2. Switch to plan B  
3. Self-host  
4. Seek in-kind help  
5. Only then consider donations for break-glass costs  

Any proposal to gate a **core** feature behind payment needs a public RFC and community vote.
