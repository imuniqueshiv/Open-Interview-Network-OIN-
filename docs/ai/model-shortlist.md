# Model and licence shortlist

Pin exact versions and **SHA-256** hashes. Confirm each licence from the project’s own repository when pinning (Phase 0 week 3). Licences below are **expected**, not yet verified for this repo.

| Job | Candidates | Expected licence | Note |
| --- | --- | --- | --- |
| Speech-to-text | Whisper tiny/base via Transformers.js; Vosk small Indian English & Hindi | MIT; Apache-2.0 | Benchmark on real student audio |
| Voice activity | Silero VAD | MIT | |
| Sentence embeddings | MiniLM or bge-small class | Apache-2.0 or MIT | Key-point coverage |
| Text-to-speech | Kokoro-82M via kokoro-js | Apache-2.0 | Browser speech synth fallback |
| Small LLM (optional) | Qwen2.5-1.5B-Instruct; SmolLM2-1.7B-Instruct; Phi-3.5-mini if strong device | Apache-2.0; Apache-2.0; MIT | Prefer over custom-licence models (Llama community, Gemma, some Qwen sizes) for fully OSS stack |
| Hindi / Hinglish | Vosk small Hindi; multilingual Whisper; e.g. Shruti | Check each | Do not assume Vosk is good enough on Hinglish |

## Device reality

- ~4-bit 1B model ≈ 700 MB download; ~900 MB GPU memory (planning figures)  
- WebGPU: Chrome Android ≥121; Safari 26+ (verify)  
- Budget phones often lack memory — capability-test before offering  
- Small models hallucinate → optional prose only; **never** scores  

## Hosting model files

1. Hugging Face primary  
2. College node mirror  
3. App verifies hash of every file (bad mirror cannot swap content)

## Lane 2 — `oin-worker`

Container pulls queued jobs, runs llama.cpp + permissive model, posts results. Browser encrypts job to node public key (libsodium sealed box); server stores ciphertext only. Planning: 4-core Arm VM, 1.5B–3B model → few–15 tok/s → order of ~1000 reports/day (assumption). Best-effort; Lane 0 never waits.
