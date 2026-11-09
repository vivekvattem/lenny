# Design and engineering decisions

These decisions explain the published prototype. They are not claims that broad answer quality or release acceptance passed. [Verification](verification.md)

| Decision | Reason and trade-off |
| --- | --- |
| A research-to-document workspace | Keep questions, source inspection, reviewed writing, and saved artifacts together. Local single-evaluator use takes priority over collaboration, billing, and production authentication. |
| Pi as the application agent | Integrate the required agent framework through its RPC/extension interfaces. Codex assists development; it is not the runtime agent. Narrow tools limit what source text can cause the agent to do. |
| Ollama by default | Keep local inference under the user’s control. Limited RAM and small models constrain speed and capability; model size alone does not establish quality. Cloud is explicit, server-configured, and never a silent rescue. |
| PostgreSQL and pgvector | Store source versions, lexical/vector retrieval data, conversations, and artifacts together. This simplifies local operation while leaving retrieval quality and query latency to be measured separately. |
| Immutable pinned corpus | Fetch a specific revision, validate manifests, and preserve exact source bytes/metadata. Source changes create new versions; missing timestamps stay unknown. Full corpus and private traces remain outside Git. |
| Embedding identity guards | Pin model/digest/dimensions/prefixes and reject incompatible indexes. Changing an embedding model requires a deliberate separate rebuild rather than mixing vectors. |
| Bounded evidence and generation | Limit context, outputs, tools, deadlines, and retries. Exact excerpts reduce invented factual prose, but quotes can still be irrelevant or incomplete; semantic support needs review. |
| Durable request/session ownership | Save prompts and run identities, prevent duplicate retries, scope sources/artifacts to their owner, and preserve completed work. Additive migrations avoid resetting normal data. |
| Evidence-first reviewed essays | Keep factual quotes and citations tied to owned sources while Pi supplies advice. The 1,208-word fixture needed nine manual edits; deterministic citation/length checks do not prove autonomous writing quality. |
| Static export rendering | Produce Markdown and complete static HTML, sanitize active content, and render HTML in a restrictive iframe/CSP. This limits interactivity in return for a smaller rendering boundary. |
| Explicit cloud budgets and credentials | Keep keys server-side, disable provider fallback, and apply model-specific request policy. The scoped GPT-OSS-120B final-answer budget has separate [wire/live evidence](openrouter-120b-output-cap-test.md); current credits are not assumed. |
| Separate verification scopes | Report unit/mock, real database, live model, browser, and semantic acceptance independently. **148/148 contracts** do not replace **0/5 acceptance**. |

The original chronological decision diary remains in [Git history before cleanup](https://github.com/vivekvattem/lenny/blob/3e783b2d14c9f14e9852dcbc266397be07feb197/docs/decisions.md). Detailed experiment narratives are omitted here; historical evidence and raw private originals remain retained.

[Architecture](architecture.md) · [Product requirements](PRD.md) · [Current limitations](known-issues.md) · [Source provenance](provenance.md)
