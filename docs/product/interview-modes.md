# Interview modes

| Mode | What it is | Phase |
| --- | --- | --- |
| **Human to human** | Browser-to-browser room: audio, optional video/avatar, captions, timer, shared notes, cards, rubric sidebar | 1 |
| **Answer drill** | Pick a card, record ≤2 min, on-device transcript + rubric report, retry | 1 |
| **Scripted-adaptive AI interviewer** | Turn-based voice interviewer from resume + bank, in browser | 3 |
| **Interviewer practice** | Score calibration clips; compare to reference scores | 2 |
| **Group discussion** | ≤4 on free path (5–6 with optional node); human moderator; topic cards; GD rubric | 3 |
| **Drive Mode** | Weekend schedule of rounds (human or AI) by company pattern | 4 |
| **AI-assisted human room** | Optional private follow-up suggestions from card ladder; both see it is on | 4 |

## Room (Phase 1)

Browser-to-browser audio; optional video; captions where supported; timer; shared notes; question cards; rubric sidebar; one-click report and leave.

## Room (Phase 2+)

Shared code editor: Monaco + Yjs. Code runs in browser (Pyodide for Python; JS in sandboxed worker). **No** code-judge server. Do **not** build aptitude tests — link to existing free resources.

## Groups

- Free path: full mesh, **max 4**, audio by default (~100 kbps upload per member sending 3 streams)
- 5–6: optional self-hosted LiveKit node — never block a 4-person room waiting for an unreachable node
- Observer: teacher/friend as listen-only 4th peer when both agree
