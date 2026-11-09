# Verification summary

This summary separates backend checks, semantic acceptance, and the manually reviewed demo. Documentation cleanup changes no runtime behavior and is not a new test run.

| Check | Recorded outcome and scope |
| --- | --- |
| Verified acceptance revision | [`d1f519eed8dfc4a0f485f79c518a554aff9ea7ad`](https://github.com/vivekvattem/lenny/commit/d1f519eed8dfc4a0f485f79c518a554aff9ea7ad), 9 November 2026 |
| Provider | Pi → local Ollama, chat `qwen3:0.6b`; no cloud substitution |
| Backend contracts | **148/148 passed**, 20.597 seconds, exit 0; unit/mock generation plus real PostgreSQL/local embedding checks on a separate test database |
| Corpus | Pinned revision `be8ab89a890a833cbba2c892178f823fff178c65`, 303 episodes / 12,770 passages in the acceptance database |
| Frozen A–E acceptance | **0/5**. Incomplete or unsupported answers, operational RPC failures, and fresh-essay quality prevented full journey passes. Contract totals are separate from this score. |
| Historical acceptance | Both earlier frozen batches also scored **0/5** against the proposed 4/5 target. No new five-scenario pass is claimed. |
| Reviewed essay fixture | **1,208 words; nine manual edits**: six application paragraphs and three evidence selections. A reviewed example, not an autonomous writing result. |
| Export integrity | Markdown and HTML matched saved artifacts and reviewed-fixture hashes; both previews and standalone HTML opened in isolated Chrome 157. No model calls or database changes during export verification. |

## Evidence boundaries

- Exact spans establish source integrity; they do not prove a quote answers the question.
- Historical full-index hybrid Recall@8 was 56.25% on tuning and 81.25% on previously observed holdout, below the proposed 85% target. The holdout is no longer unseen.
- Historical local smoke and restart/reopen checks used a three-interview index. Their success does not replace full-index acceptance.
- A historical OpenRouter GPT-OSS-120B question/follow-up pair produced supported citations. This does not verify present credentials, credits, or broad cloud quality. [Scoped cloud check](openrouter-120b-output-cap-test.md)
- Local resource pressure, retrieval/RPC reliability, answer completeness, unsupported-request handling, and unedited essay quality remain limitations. RAM is not a proven explanation for every failure.
- Sanitized command logs and review summaries are available. A complete sanitized coding conversation export is unavailable.

[Reviewed exports and exact hashes](demo/verification.md) · [Manual test plan](test-plan.md) · [Sanitized build evidence](agent-transcripts/README.md)

Phase narratives and duplicate planning documents were removed from the current tree. Original records remain in [Git history before cleanup](https://github.com/vivekvattem/lenny/tree/3e783b2d14c9f14e9852dcbc266397be07feb197/docs). Tests, underlying sanitized evidence, and demo export bytes are preserved.
