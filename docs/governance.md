# Open-source governance, licensing and naming

## Licences

| Asset | Licence |
| --- | --- |
| Main application | AGPL-3.0 |
| Reusable libraries (avatar kit, rubric spec, interview-engine schema, Coach) | Apache-2.0 |
| Question content | CC BY-SA 4.0 |
| Model weights / datasets | Explicit per-artefact licence |

AGPL means changes to a **hosted** version must be shared — protects against closed forks. A college running its own copy is unaffected. Check dependency licence compatibility when pinning (stack is mostly MIT / Apache-2.0).

## Contributors

- **DCO sign-off** (not CLA) unless dual-licence later — see [CONTRIBUTING.md](../CONTRIBUTING.md)  
- Publish CONTRIBUTING, Code of Conduct, SECURITY, public roadmap  
- Start maintainer-led; add RFC process + `MAINTAINERS` as contributors arrive  
- Providers behind adapters; secrets out of the repository  

## Naming

“Open Interview Network” is generic. Search the trademark registry and existing projects **before** building brand (searching is free). Consider a more distinctive name. File trademark later if the project grows; use the name consistently; publish a short trademark policy so forks cannot pass as the official service.

## Entity

Not needed while no money is received. When a grant/donation requires one: Section 8 company or trust — ask a chartered accountant. Publish income and spending.

## Team (Phases 0–2)

| Role | Who | Focus |
| --- | --- | --- |
| Product & community lead | You | Decisions, pilots, partnerships, interviewer recruitment |
| Full-stack engineer | Contributor 1 | Room, matching, scheduling, cohort dashboard, quota governor |
| Real-time & on-device AI | Contributor 2 | WebRTC, avatar, STT, Coach, evaluation set |
| Designer / UX writer (PT) | Contributor 3 | Flows, Hindi copy, a11y, kits |
| Campus partnerships | Senior student / alumnus | Pilot logistics, Nights, ambassadors |
| Moderators / trainers | Volunteers above trust threshold | Reports, certification, quality |

## Operating rhythm

- **Weekly:** north star, connect rate, no-show, quota headroom; Night retro; bug triage  
- **Monthly:** quota/provider review; moderation summary; backup restore; interviewer quality sample  
- **Quarterly:** impact report + aggregate moderation; chaos drill  

Two admins on every account; written handover note so one person leaving never locks the project out.
