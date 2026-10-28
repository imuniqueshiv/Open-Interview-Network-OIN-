# AI at zero cost — principles and lanes

## Principles

1. AI never replaces human practice; it fills gaps between human sessions.  
2. Compute where it is free: on the learner’s device.  
3. Deterministic first, generative last — scores/coverage from testable code; LLMs only optional labelled prose.  
4. Every lane except **Lane 0** is optional; product works with others off.  
5. Nothing that identifies a person leaves the device unless they choose to send it.

## Four lanes

| Lane | What | Where | Cost | Phase |
| --- | --- | --- | --- | --- |
| **0 Coach engine** | Delivery metrics, structure, key-point coverage, templated feedback + evidence | Browser (JS / Wasm) | ₹0 (~30–60 MB one-time — assumption) | 1 |
| **1 On-device models** | STT (Whisper class), TTS (Kokoro), optional small LLM | Browser WebGPU / Wasm | ₹0 (~40–200 MB STT; ~0.7–1 GB+ LLM) | 1 STT; 3 rest |
| **2 Community compute** | Longer reports / batch via llama.cpp | College PC or free VM (`oin-worker`) | Donated HW; queued | 3 |
| **3 Free-API overflow** | Short summary if 0–2 unavailable | Cloudflare Workers AI free allocation | Within allowance; **off by default** | 3 |

Lane 3 constraints: de-identified text only, per-use consent, global daily cap. Prefer Workers AI over free tiers that train on prompts (confirm Cloudflare data-use page; Gemini free tier trains — fine for maintainers drafting **public** card text with no personal data).

## Scripted-adaptive AI interviewer (Phase 3)

- Resume read on device (PDF.js); tag match → 6–10 topics; learner corrects list; resume = untrusted data, never instructions  
- Loop: speak (Kokoro / browser TTS) → listen/transcribe → coverage → follow-up ladder or next topic; state machine owns time/difficulty  
- Optional on-device LLM only rephrases wording  
- Expect **2–4 s** between turns on mid-range devices (assumption)  
- Cap 45 minutes; screen says it is AI  
- More reliable than hosted voice agents: no network after first load; unit-testable decisions  

## Interviewer practice without AI candidate

Calibration clip library with reference scores — deterministic fairness training.

## Own model (staged)

1. Phases 1–3: open-weight + rules; no training  
2. Phases 3–4: consented de-identified human-rated evaluation set (the real asset)  
3. Phase 5: fine-tune small model / scoring classifier if it beats baseline  
4. Publish weights, dataset card, evaluation; credit donors  

Rules: [../privacy/data-protection.md](../privacy/data-protection.md) § model training.
