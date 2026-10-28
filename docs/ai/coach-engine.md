# Answer drill and Coach engine (Phase 1)

## Flow

1. Learner picks a card (or app picks for weakest criterion). 2-minute timer.  
2. Browser records locally — audio never leaves device.  
3. Silero VAD marks speech/pauses.  
4. STT locally, preference order:  
   - Whisper-class via Transformers.js (WebGPU/Wasm)  
   - Vosk small (Indian English / Hindi) ~50 MB  
   - Browser on-device speech recognition **only** if it reports local (`processLocally`)  
   - “Type your answer” fallback  
   - **Never** silently use cloud browser speech recognition  
5. Learner may correct transcript before scoring.  
6. Coach computes metrics below.  
7. Learner self-scores first, then sees report.  
8. Report: three strengths, three gaps, one next drill — each with evidence sentence + timestamp. Say “not assessed” when unsure.  
9. Optional “Explain in more detail”: Lane 1 → 2 → 3 (consent) → nothing. Numbers never change.  
10. Audio discarded at end. Transcript on device only if saved. Only numeric scores sync if signed in + opted in.

## Metrics

| Metric | How | Note |
| --- | --- | --- |
| Pace | WPM from transcript + speech time | Target band = assumption; tune on gold set |
| Filler rate | Fillers/min (EN + common Hinglish) | Hinglish switching never penalised |
| Pauses | Long-pause count + silence share from VAD | |
| Length | Duration vs card target | |
| Structure (STAR) | Lexical cues + order | Heuristic: detected / not detected |
| Ownership | Share of “I” vs “we” | Prompt to clarify contribution — not honesty score |
| Specificity | Numbers, tools, project names vs card tags | |
| Key-point coverage | Card lists 3–6 points; MiniLM/bge-small class embeddings (~25–35 MB quantised); threshold on gold set → covered / partly / not detected | Highlight matched sentence; learner can override |

## Quality bars

- Gold set ~30 sessions Phase 0 → ~100 later  
- Ship new model/threshold only if human agreement does not drop; publish numbers  
- Scores ignore accent, name, gender, college  
- No hire / no-hire verdict; show confidence  
- Hinglish: measure on ≥200 answers (assumption); enable only above bar  
- Label all software-written/spoken content  
