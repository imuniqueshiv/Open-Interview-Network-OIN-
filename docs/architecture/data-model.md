# Data model and security (short)

## Main tables (planned)

`profiles`, `comfort_prefs`, `availability`, `sessions`, `session_participants`, `feedback` (rubric scores as JSON), `question_cards`, `card_versions` (public), `certifications`, `reports`, `blocks`, `cohorts`, `consents`, `quota_counters`, `client_errors`.

## Rules

1. **No table stores audio, video, transcripts, or resumes by default.** Those stay on the learner’s device.
2. **RLS on every table**, written and tested before any feature uses it. Postgres test suite in CI.
3. Cohort dashboards are views over **numeric scores** only; groups below minimum size (**assumption:** 10) are not shown.
4. Secrets (TURN token, SMTP key) live only in Edge Function secrets and GitHub secrets.
5. Two admins on every account; 2FA everywhere.
6. CC BY-SA content is public; everything else private to its owner.

## Client-only storage

- Drill audio: process then discard when drill ends  
- Transcript: IndexedDB only if learner saves  
- Numeric scores: sync to server only if signed in **and** opted in  

## Schema practice

Keep schema as **plain SQL migrations** so self-host and hosted Supabase stay identical.
