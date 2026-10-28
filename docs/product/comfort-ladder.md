# Comfort ladder and avatar

Each person picks their level and can change anytime. **Nobody can force a partner upward.**

| Level | Partner sees | Needs | Ships |
| --- | --- | --- | --- |
| 1 | Still avatar or initials; voice only | Audio | Phase 1 |
| 2 | Avatar lip-syncs to voice; no camera | Audio | Phase 3 (after spike) |
| 3 | Avatar mirrors expressions; camera used **on device only** — no video leaves device | Camera + tracking | Phase 3 (after spike) |
| 4 | Real video, only if **both** choose it | Camera | Phase 1 |

Nudges over time (“five sessions at level 2 — try 3”) because the goal is confidence on a real video call, not a permanent mask. Avatars also reduce appearance cues for fairer evaluation.

## How level 3 works (zero server cost)

1. MediaPipe Face Landmarker in the browser → 52 blendshape scores/frame.
2. Small packets over unordered WebRTC data channel (drop late packets).
3. three.js VRM avatar on partner device reproduces expression.
4. Levels 1–2: mouth from browser audio analyser.
5. No camera frame leaves the device; blendshapes never stored on our servers.

## Sync and performance

- Timestamp packets against audio clock; delay render to match playout (~100 ms target).
- If device cannot hold ~20 fps, auto-drop to level 2.
- Tracking in a web worker; offer audio-only low-bandwidth mode.

## Avatar rules

- CC0 / properly licensed stylised VRM library + original team assets (check every licence)
- No uploads of a real likeness
- Visible “avatar mode” badge; captions on
- Never store blendshape streams or frames

## Spike go/no-go (assumptions)

- Median ≥20 fps on mid-range Android
- Median sync ≤150 ms; p95 ≤250 ms
- Ask students: helpful training wheel or gimmick?

If spike fails: ship levels **1 and 4** only; product still works.
