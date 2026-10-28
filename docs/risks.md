# Risks and mitigations

| Risk | Why it matters | Mitigation |
| --- | --- | --- |
| Free tier changes / disappears | Core services on third-party free plans | Adapters, quota governor, backups, self-host bundle, [provider playbook](operations/provider-playbook.md) |
| Calls fail on college networks | Firewalls block UDP | TURN TLS 443; second TURN; paste-a-link; H8 in Phase 0 |
| Supabase pauses | Week of inactivity | Keepalive, traffic, wake runbook, backups |
| On-device AI weak on budget phones | Equity gap | Small Lane 0 models; typed fallback; college nodes / lab mode; measure by device |
| Large first downloads | Mobile data cost | Ask first; show size; prefer Wi-Fi; campus mirror |
| Avatar / lip-sync uncanny or laggy | Comfort promise fails | Phase 0 spike; not critical path; levels 1 & 4 work alone |
| Weak peer interview quality | Trust loss | Kits, certification, seniors/alumni |
| Cold start | Empty network ruins first impression | Solo drills; one college; weekly Night; hand matching Phase 0 |
| Unfair scoring / poor Hinglish | Wrong feedback trusted | Rubric, gold set, group checks, accuracy bar, editable transcripts, evidence |
| Harassment or scams | One incident can end trust | [trust-safety.md](trust-safety.md), moderators, campus pools, 18+ |
| DPDP non-compliance / earlier timeline | Full rules by May 2027, maybe sooner | Minimal collection; on-device sensitive data; full standard now; legal review |
| No money for surprises | No budget | No card attached; break-glass list; federation |
| Seasonal demand | Spike with drives, fall after | Calendar; working-professional track off-season |
| Over-reliance on avatar | Permanent mask ≠ real interview readiness | Ladder nudges toward real video |
| Maintainer burnout | Student-led stall | Small scope; shared maintainers; two admins; handover notes |
| Funded competitor forks | OSS allows it | AGPL; consistent name use; community & institution relationships |
