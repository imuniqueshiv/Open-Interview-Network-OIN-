# Data protection and privacy

Privacy is a product feature: voice, resumes, and practice mistakes. Sensitive data **never reaches a server by default** because drills and the AI interviewer run on device.

| Data | Default handling | Used to train models? |
| --- | --- | --- |
| Account / profile | Pseudonymous display name; kept until deletion | No |
| Resume / extracted fields | On device; never uploaded unless shared with one chosen partner | Never |
| Camera frames | On device; never uploaded/stored | Never |
| Blendshape stream | Peer-to-peer; never stored | Never |
| Live audio | Peer-to-peer; not recorded by OIN | Never |
| Drill audio | On device; discarded when drill ends | Never |
| Transcript | On device only if saved | Only with separate de-identified opt-in |
| Scores / feedback | Numbers in history; member + partner | Only de-identified + opt-in |
| Lane 2 / 3 jobs | De-identified; Lane 2 encrypted; per-use consent | No |
| Question bank | Public under content licence | Yes (public) |

## India’s DPDP timeline

- DPDP Rules notified **13 Nov 2025**  
- Most operational duties start ~**13 May 2027** (18 months)  
- MEITY has consulted on shortening some timelines — treat May 2027 as **latest**, not planning date  
- Meet full standard before pilot grows beyond ~100 students  
- Get legal-clinic / volunteer lawyer review before public launch  

Sources checked 28 Oct 2026: Bar & Bench, Konfirmity, Mondaq, Storyboard18 — confirm current law yourself.

## Design consequences

- Itemised notice and consent (EN + HI), never bundled; withdrawal as easy as consent  
- Erasure and export from settings; named grievance contact; published response times (Rules cap grievances at 90 days)  
- Breach runbook: notify Board + users without delay; detailed report within 72 hours; CERT-In cyber incidents within six hours of knowledge  
- Name the data fiduciary for the public instance; college self-hosts are fiduciaries for their instances  
- **18+ only** at launch (verifiable parental consent for under-18)  
- Retention: Rules require certain logs ≥1 year for specified government purposes — check with counsel  
- Prefer India regions on free plans (e.g. Supabase Mumbai if available); publish sub-processors (Cloudflare, Supabase, Brevo, GitHub, Hugging Face, …)  

## Rules for building our own model

- Separate opt-in per data type; revocable for **future** use  
- Say plainly a published model cannot un-learn earlier data  
- No voice/video in datasets at launch  
- Scrub names, colleges, employers, contact details  
- Do not rely on a research exemption (unclear under Rules)
