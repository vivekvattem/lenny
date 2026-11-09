# Manually reviewed essay fixture — verification

[Markdown export](manually-reviewed-essay.md) · [HTML export](manually-reviewed-essay.html)

**Historical manually reviewed example: 1,208 words, six sections, nine manual edits. This is not an autonomous or freshly generated essay. The frozen A–E acceptance result remains 0/5.**

The saved session was labelled **Demo — Reviewed essay · reviewed example · 1,208 words · 9 manual edits**. The historical edits comprised six application-paragraph rewrites and three evidence-span edits. Neither export was edited for this publication: the filenames and this summary label the provenance while preserving the original artifact bytes.

## What was verified

Re-exported on 9 November 2026 from the isolated workspace used for acceptance revision [`d1f519eed8dfc4a0f485f79c518a554aff9ea7ad`](https://github.com/vivekvattem/lenny/commit/d1f519eed8dfc4a0f485f79c518a554aff9ea7ad).

- Markdown content exactly matches the saved assistant message and saved Markdown artifact.
- HTML content exactly matches the saved complete static HTML artifact.
- Both files match the locked reviewed-fixture hashes; actual essay count remains 1,208 under the project's existing word-count method.
- Six saved source mappings, pinned corpus identity and all owned quoted-span hashes matched the reviewed-fixture record. These are integrity checks, not automatic semantic proof.
- Both previews opened in isolated Chrome 157 with six headings, all six citation labels, the fixture disclosure and an empty iframe sandbox. Their normalized visible text matched. The exported HTML also opened independently with the same visible text.
- Zero model calls, zero application/database writes, zero workspace page/console errors during this export check. The saved session and artifacts remained unchanged. No new generation, essay acceptance, model download or cloud fallback.

Export checked at **09 November 2026, 18:50:57 IST**; browser check **18:51:54 IST**. The source report and raw verification evidence remain private; this is a sanitized summary, not a raw log or reconstructed transcript.

## Exact exported bytes

| File | Bytes | SHA-256 |
| --- | ---: | --- |
| `manually-reviewed-essay.md` | 7456 | `622acbd2368356f8cd4ea5103383fc428539aa4b8093f78194bc780598b7693f` |
| `manually-reviewed-essay.html` | 8786 | `91ea1f66278d0d25638eb51074c1960340a57ceaf9229028d6f57397ceb9c022` |

Download the HTML file and open it locally; GitHub's file view displays its source rather than hosting it as an application. The Markdown file can be read directly on GitHub.

## Public source references

All six labels refer to Sean Ellis's interview, **The original growth hacker reveals his secrets | Sean Ellis (author of “Hacking Growth”)**, in pinned corpus revision `be8ab89a890a833cbba2c892178f823fff178c65`. Transcript file SHA-256: `6af2a6e031826805e855ec262b1f228e3773b5b99265a1d01870f0d4e6e9ceda`.

The links below use the saved passage line ranges. They link source context, not a new claim-by-claim quality evaluation.

| Citation | Saved passage lines |
| --- | --- |
| [S2](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L39-L64) | 39–64 |
| [S3](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L229-L248) | 229–248 |
| [S4](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L151-L170) | 151–170 |
| [S5](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L136-L151) | 136–151 |
| [S6](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L103-L116) | 103–116 |
| [S7](https://github.com/ChatPRD/lennys-podcast-transcripts/blob/be8ab89a890a833cbba2c892178f823fff178c65/episodes/sean-ellis/transcript.md#L442-L457) | 442–457 |

Some historical edited inline essay facts do not have a corresponding exact span in the saved source annotations. Their original passage can be inspected, but exact UI highlighting is unavailable for those facts; no location or missing annotation was invented for this publication. The export bodies and saved evidence remain unchanged.

## Acceptance failures remain 0/5

The reviewed fixture is separate from the fresh acceptance essay. At the verified revision, **148/148 backend contracts passed** in 20.597 s (exit0) on a separate test database; those checks included unit/mock generation plus real PostgreSQL/local embedding scopes. They do not establish answer/essay quality. The full pinned index contained 303 episodes/12,770 passages. Neither the backend suite nor A–E was rerun for this publication.

| Case | Result | Recorded failure |
| --- | --- | --- |
| A | FAIL | Unsupported survey conclusion and incomplete use-of-responses answer. |
| B | FAIL | Incomplete/conflated LNO explanation; requested bug-triage checklist missing. |
| C | FAIL | Fresh unedited 1,204-word essay passed format/count screens but failed support, hook, progression and takeaway review. |
| D | FAIL | Both independent requests returned `rpc_rejected`; no supported answers/artifacts. |
| E | FAIL | Unsupported request returned `rpc_rejected`, not an abstention after successful retrieval. Its reformulation completed, but that did not pass the full journey. |

The initial E preflight also returned 503 `agent_unavailable` before inference; it recovered without code/config changes. Original failures remain in private evidence. All task caps were met, but operational/semantic gates failed. No release-quality or autonomous-writing pass is implied by this reviewed fixture or the passing contracts.

This demo publication includes the two reviewed essay exports, this sanitized summary and README links. The two rejected chat demos, raw logs/API payloads, private traces/screenshots, credentials, corpus/database files and unpublished frontend review work are excluded.
