# Cost model — zero rupees by design

## Operating cost (core loop)

| Need | v1.1.2 approach | Cost to project |
| --- | --- | --- |
| Human-session media | Browser-to-browser; free STUN/TURN | ₹0 |
| Speech-to-text | On learner’s device | ₹0 |
| Answer scoring | Coach engine on device | ₹0 |
| Live AI interviewer | Scripted-adaptive in browser | ₹0 |
| Database & sign-in | Supabase free | ₹0 |
| Static hosting | Cloudflare Pages + GitHub Pages | ₹0 |
| Email | Brevo free SMTP (300/day) | ₹0 |
| Reminders | Push, Telegram, calendar files | ₹0 |
| CI / status / backups | GitHub Actions, Upptime, private repo | ₹0 |
| Bot protection | Turnstile | ₹0 |

## Things that cost money everywhere — free routes

| Item | Free route | What you give up |
| --- | --- | --- |
| Custom domain | Free Pages subdomain; student programmes if eligible | Memorable address |
| Legal review | Law-school clinic / FOSS legal aid / volunteer lawyer | Professional assurance |
| Company / society / trust | Operate as OSS project or college club until money arrives | Ability to receive money |
| Trademark filing | Free registry search; consistent use; file later | Weaker brand protection |
| Test phones | Borrow; OSS device programmes | Coverage |
| Moderator / interviewer stipends | Certificates, references, thanks; cap hours | Retention risk |
| Paid ads | Placement cells, clubs, demos, alumni | Slower early growth |

## Strongest cost control

**Never attach a payment method to any account.** Crossing a free limit degrades service instead of creating a bill — paired with the quota governor.

## Break-glass (not planned)

Cheapest paid steps found for reference only (verify current prices):

- Supabase Pro ~$25/month  
- Cloudflare Workers Paid ~$5/month  
- Cloudflare TURN ~$0.05/GB beyond first 1,000 GB  

Prefer self-hosting first.

## Sustainability without payments

- Institutions contribute interviewers, lab, node, cards, coordinator — not money  
- Donation page optional; entity required before receiving money  
- If money arrives, spend order: domain → test devices → break-glass headroom → legal → volunteer honoraria; publish ledger  
- **Never monetise:** private resumes/transcripts/voice; ads; recruiter access (except one shared profile); paywalls on human interviews; buying XP/badges/trust  
- Licence may allow third parties to offer paid hosting; the project itself stays free  
