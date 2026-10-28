# Account and setup checklist (all free)

Create every account with a **shared project email**, **two admins**, **2FA**, and **no payment method**. Store secrets in GitHub Actions secrets and Supabase function secrets only. Team password manager: Bitwarden or KeePassXC (open source).

| Service | Used for | Card needed? | Notes |
| --- | --- | --- | --- |
| GitHub (org, public repo, private backup repo) | Code, CI, Pages mirror, Upptime, backups | No | Branch protection + secret scanning |
| Cloudflare | Pages, TURN keys, Turnstile, optional Workers | No for these products (Realtime page: no card — confirm) | TURN key token → Edge Function secret |
| Supabase | DB, auth, realtime, Edge Functions | Expected no; confirm | Prefer Mumbai region if offered; Brevo as custom SMTP; keepalive workflow |
| Brevo | Free SMTP (magic links, reminders) | No (per sign-up page) | Verify sender; expect Brevo branding on free plan |
| Google Cloud project | OAuth for “Sign in with Google” | Confirm OAuth client needs no billing | If it does, launch with email links only |
| Telegram | Reminder bot | No | BotFather |
| Hugging Face | Model file hosting | No | Mirror on college node as plan B |
| Oracle Cloud (optional) | Backup coturn, LiveKit &gt;4, `oin-worker` | Confirm: sign-up may ask card for identity | Skip if card required; keep busy to avoid idle reclaim |

## Lab checklist (Phase 0)

Two low-end phones · one mid-range Android · one lab PC · college Wi-Fi · mobile data · headset.
