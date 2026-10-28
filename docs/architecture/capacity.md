# Capacity envelope of one free deployment

**All figures are estimates** from published free allowances + assumed **3 human sessions per learner per month**. Replace with Phase 1 load-test measurements.

| Resource | Free allowance | Use per 1,000 MAU | Comment |
| --- | --- | --- | --- |
| Concurrent realtime connections | 200 | Peak ~60–100 on a Mock Interview Night | **First limit:** ~100 sessions at once |
| Realtime messages | ~2M / month | ~3,000 sessions × 60 msgs ≈ 180k | ~10× headroom |
| Database | 500 MB | ~3,000 × 10 rows × 0.5 KB ≈ 15 MB / month | Trim/aggregate rows &gt;12 months |
| Database egress | 5 GB / month | &lt;1 GB if question bank is static | Keep bank off DB |
| TURN egress | 1,000 GB / month | If 20% relay: ~3,000 × 0.2 × 18 MB ≈ 11 GB audio | Audio 32 kbps ≈ 7 MB/direction/30 min before overhead |
| Email | 300 / day | ~6,000 reminders/month ≈ 200/day if all email | **Second limit** — push/Telegram must carry ≥ half |
| Lane 3 overflow | ~450 short reports/day (planning) | Off unless needed | Opt-in only |

## Conclusion (assumptions)

One free deployment comfortably supports about **1,000 MAU**, probably up to about **3,000**, with about **100** simultaneous sessions. Beyond that: **more instances** (college self-hosting), not payment.
