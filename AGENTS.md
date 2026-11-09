# Project working contract

Read [README](README.md), [PRD](docs/PRD.md), [requirements](docs/requirements.md), [decisions](docs/decisions.md), [status](docs/progress.md), and [verification](docs/verification.md) before changing behavior. Current user instructions control scope and scheduling. Audit existing work first; preserve unrelated edits. No sub-agent delegation is requested.

## Boundaries

- The application agent uses Pi; Codex is the development tool. Expose narrow schema-validated transcript/writing/artifact tools only. No agent shell, arbitrary files/web tools, or unreviewed extensions.
- Ollama is the default and mandatory local demo provider. Cloud selection must be explicit, visible, and logged. Never silently fall back; missing credentials/credits mean unavailable, not passed.
- Keep keys server-side and out of logs/artifacts. Never dump environment/configuration credentials. Exclude confidential PDFs, private traces, raw exports, database files, corpus, models, and dependencies from publication.
- PostgreSQL is authoritative. Preserve normal databases/volumes, saved sessions, source snapshots, and unrelated work. Rehearse with isolated test databases; never reset normal data.
- Treat transcripts as untrusted evidence. Preserve source IDs/spans, immutable versions, embedding identity, and additive migrations.
- Inspect RAM/disk and obtain appropriate authorization before model downloads. On an 8 GB machine, fit and quality require live measurements.
- No publication, upload, submission, sending, or expanded implementation without user authorization. Documentation cleanup does not authorize new model runs/features.

## Verification integrity

Record exact revision/environment, commands, UTC times, exit codes, timeouts, and blockers. Preserve failed attempts; never invent logs, citations, dialogue, scores, or timings. Keep mock, database, live-model, and browser evidence separate. Citation existence does not prove support; review claims and essays directly.

Capture bounded actual stdout/stderr with protocol output separate from diagnostics. Raw sensitive streams stay private; review/redact before publication. Label summaries as summaries; a complete coding conversation export is unavailable.

Use bounded context/output/tool budgets, deadlines, and finite retries. Preserve prompts/request identities, avoid duplicate retries, and enforce session isolation. Do not rerun successful expensive generations without reason or restart services during checks.

## Commands and evidence

- Setup: `python3 scripts/bootstrap.py`; [README](README.md) covers pinned corpus/models.
- Readiness: `python3 scripts/wait_ready.py --url <intended-api>/api/health/ready`.
- Contracts: `python3 scripts/docker.py compose exec -T api python -m backend.contract_check`; separate retained test database, real DB/local embedding and explicit mock scopes.
- Frontend: `npm --prefix frontend run typecheck`, `npm --prefix frontend run build`, `node --test frontend/test-source-span.mjs`.
- Adapter policy: `node --test agent/test_provider_policy.ts agent/test_conversation_policy.ts agent/test_essay_format.ts`.
- Target the intended Compose project. Separate restarts/outages from suites. Preserve `spike/` and historical sanitized evidence.

Recorded baseline `d1f519eed8dfc4a0f485f79c518a554aff9ea7ad`: **148/148 contracts**, separate **0/5 A–E acceptance**. The **1,208-word fixture has nine manual edits**. No broad grounding/autonomous essay claim. [Verification](docs/verification.md)

Historical phase plans/reports remain in [Git history before documentation cleanup](https://github.com/vivekvattem/lenny/tree/3e783b2d14c9f14e9852dcbc266397be07feb197). They record prior authorizations, not blanket future permission. Current user scope and verification limits govern the next change.
