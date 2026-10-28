# Phase 0 — Validate (2–30 Nov 2026)

Prove or kill the riskiest assumptions **before** building product. Plan around festival weeks when students are less available.

**Gate (30 Nov):** review the go/no-go note against [ROADMAP.md](../ROADMAP.md) Phase 0 criteria.

## Week 1 (2–8 Nov) — Accounts, call, students

- [ ] Create free accounts per [operations/account-checklist.md](operations/account-checklist.md) — **two admins each, no payment method**
- [ ] Spike: two browsers connect via Supabase signaling + plain peer-to-peer call
- [ ] Test on home broadband, mobile data, and one college network
- [ ] Avatar spike: webcam → MediaPipe → blendshapes → VRM on one page; FPS on three devices (incl. mid-range Android)
- [ ] Interview **15 students** on H1 (camera fear) and H3 (who would interview)

## Week 2 (9–15 Nov) — Relay, speech, scoring

- [ ] `ice-servers` Edge Function with Cloudflare TURN; force relay on UDP-blocked network
- [ ] Record connect rate (H8) and relay share
- [ ] Avatar packets over data channel; measure sync offset vs audio
- [ ] Benchmark in-browser STT (Whisper tiny/base, Vosk small) on 3 devices × ~30 recordings: WER, time, memory
- [ ] Prototype Coach engine on 2 cards × 20 answers; compare coverage to 2 human raters (early H7)
- [ ] Hand-match 10 students (early H2)

## Week 3 (16–22 Nov) — Project setup

- [ ] Monorepo hygiene: licence files, CONTRIBUTING, CoC, SECURITY, public roadmap *(this repo)*
- [ ] Turn on Actions, Upptime, nightly encrypted backup; run **one restore drill**
- [ ] Decide licence, name, 18+ rule; trademark registry search
- [ ] Pin model versions + SHA-256; confirm licences from upstream repos
- [ ] Draft privacy notice + consent screens (EN + HI); ask legal-aid clinic / volunteer lawyer
- [ ] Interviewer Kit v0: campus technical + HR/behavioural (~10 cards each, 3–6 key points); **6 calibration clips** + reference scores
- [ ] Prototype quota governor with fake usage

## Week 4 (23–29 Nov) — Pilot line-up + manual Night

- [ ] Meet one placement cell (+ backup) with one-page offer: 50–100 students, 2 coordinators, 10–15 interviewers, weekly Night, optional college node; ask for drive calendar
- [ ] Recruit 10–15 teachers/seniors; run 20-minute kit training
- [ ] Hold **one manual Mock Interview Night** (meeting tool or lab) with kit + paper rubric
- [ ] Publish 60-second demo video
- [ ] Write one-page go/no-go: free stack (H8, STT, drill time), Coach (H7), avatar, interviewer supply, institution interest

## Lab checklist

- Two low-end phones, one mid-range Android, one lab PC
- College Wi-Fi + mobile data + headset

## Spike thresholds (avatar — assumptions; tune in Phase 0)

- Median ≥20 fps on mid-range Android
- Median sync offset ≤150 ms; p95 ≤250 ms
- If fail: ship levels 1 and 4 only; revisit later

## Pass bars to record

| Check | Bar |
| --- | --- |
| H8 connect | ≥95% within 30s |
| Drill report | ≤60s on mid-range phone |
| STT | WER ≤25% (assumed) on Indian-English student audio |
| H1 | ≥8/15 say avatar/voice helps |
| H3 | ≥10/15 complete two committed sessions |
| H7 (early) | Direction toward ≥70% coverage agreement |
| Institution | ≥1 placement cell wants pilot |
