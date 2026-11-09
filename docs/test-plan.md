# Test plan

Use the exact commands in the [README](../README.md). Run database checks against the intended isolated Compose server, and keep test databases retained. Do not restart containers during tests or model operations.

## Automated checks

- Backend contracts cover API/schema/persistence, source ownership, provider policy, and artifact behavior with explicit mocks plus real PostgreSQL/local embedding scopes. They are not all live-model tests.
- Node checks cover the retrieval/conversation/provider/Markdown adapter policies.
- Frontend typecheck/build and exact-source-span tests cover static correctness and quote location.
- Historical browser fixtures and hostile-artifact checks are separate from live inference evidence.

Recorded totals and semantic outcomes are in the [verification summary](verification.md): **148/148 backend contracts**, separate **0/5 frozen A–E acceptance**. This documentation change reruns no model suite.

## Manual evaluator checks

| Journey | Check |
| --- | --- |
| Startup | Fresh isolated project/ports, bounded readiness, intended provider/models, actual corpus counts |
| Live chat | Fresh session/question, actual provider/model, completed answer; inspect each claim against the original quote |
| Follow-up and multiple parts | Correct session context and scope, every requested part addressed, separate support for each claim |
| Unsupported request | Successful retrieval followed by explicit insufficient-evidence response; infrastructure errors are not abstentions |
| Sources | Exact quote highlighting, guest/episode/timestamp when present, focus/return behavior |
| Essay | Freeze rubric/input/deadline first; score fresh unedited output and disclose every later manual edit separately |
| Export | Open Markdown and static sandboxed HTML, compare saved content, reopen both after isolated restart |
| Session isolation | Independent sessions keep messages, sources, and artifacts separate |
| Responsive/keyboard | Desktop and narrow screens, readable full answers/composer, keyboard focus and citation return |
| Failure/recovery | Bounded cancel/timeout/retry/disconnect and dependency recovery, without normal data resets |
| Privacy | No frontend keys, raw private trace uploads, arbitrary agent tools, or unsafe artifact script/network access |

Record actual revision, input, scope, provider/model, deadlines, timing, and result. Preserve first failures and corrections separately. Do not tune against an observed holdout and call it unseen; do not substitute a reviewed fixture or readiness check for a live pass. No physical-device, all-browser, independent-user-study, or broad autonomous-quality claim is implied by prior checks.
