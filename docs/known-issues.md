# Current limitations

Lenny is a local research prototype. Frozen acceptance is **0/5**, separate from **148/148 passing backend contracts**. [Verification scope](verification.md)

| Limitation | Practical impact |
| --- | --- |
| Answer completeness and relevance | A real quote may omit part of a question or fail to answer it. Review the original passage before reusing the answer. |
| Unsupported requests | Abstention is not reliable across all requests. Retrieval/RPC errors are operational failures, not evidence-based abstentions. |
| Unedited essay quality | Length and citation checks do not establish support or readability. The published 1,208-word example required nine manual edits. |
| Local resources and reliability | An 8 GB machine has limited model capacity alongside Docker and the browser. Slow requests, timeouts, and intermittent readiness failures have been observed; their causes need individual diagnosis. |
| Cloud availability | OpenRouter requires explicit server configuration and usable credentials/credits. Historical success is not a current availability check. No silent fallback. |
| Verification coverage | Chrome checks do not establish compatibility with every browser/device. Complete coding conversation export remains unavailable. |
| Deployment and source rights | A local evaluator workspace without production authentication. Full transcript redistribution rights remain unconfirmed; corpus, keys, and private runtime traces are excluded. |

See the [test plan](test-plan.md) for separate infrastructure and semantic checks, and [troubleshooting](troubleshooting.md) for recovery without resetting saved data.
