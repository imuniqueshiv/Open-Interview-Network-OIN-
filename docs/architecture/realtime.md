# Real-time design

## Joining

1. Match creates a `sessions` row.
2. Both members join a private Realtime channel for that session (RLS: participants only).
3. Exchange offers with the standard **perfect negotiation** pattern.

## Connectivity

Edge Function `ice-servers` returns:

- Cloudflare STUN  
- Short-lived Cloudflare TURN credentials (assume ~1 hour life)  
- Optional plan-B coturn  

Before issuing credentials it checks:

- Quota governor ([../operations/reliability.md](../operations/reliability.md))  
- Member daily relay allowance (**assumption:** 60 relayed minutes/day)  

Include TURN over **TLS on port 443** — college firewalls often block UDP.

## Media

- Opus audio ~32 kbps with in-band FEC and silence suppression  
- Video **off by default**; when on, cap ~300 kbps / 360p  
- Sustained high loss/delay ~10s → suggest audio-only  

## Reconnects

- Auto-restart on network change (mobile)
- 60-second rejoin window  
- Timer uses **server timestamps** so rejoin never resets it  

## Data channels (encrypted by the peer connection)

| Channel | Purpose |
| --- | --- |
| `notes` | Yjs updates |
| `tracking` | Avatar blendshape packets |
| `control` | Timer, rubric visibility, end session |

## Failure modes

| Failure | Behaviour |
| --- | --- |
| Signaling down mid-call | Call continues (media is P2P) |
| Database paused | No new sessions; show status page; offer paste-a-meeting-link + local timer/rubric |
| TURN exhausted | Direct-only (assumption: ~4/5 calls still work); degrade gracefully |

## Groups

- ≤4 full mesh, audio default  
- 5–6 need optional LiveKit node  
- Never block a 4-person room on unreachable node  

## Trust model (state plainly in privacy notice)

- We broker signaling connections between users  
- Media is encrypted browser-to-browser  
- Cloudflare TURN relay: connection metadata only, not encrypted content (per their FAQ — reconfirm)
