# Setup and handoff

Start with the [README](../README.md). Preserve an existing installation’s Compose project, ports, `.env`, database/trace volumes, and saved work. Never use `down -v`, drop a normal database, or change an index identity to hide a mismatch.

## Isolated setup

For a new evaluator installation beside an existing instance, choose unused ports and a unique project before bootstrap:

```sh
export COMPOSE_PROJECT_NAME="lenny_eval_$(date +%Y%m%d%H%M%S)"
export POSTGRES_DB="$COMPOSE_PROJECT_NAME"
export WEB_HOST_PORT=18100
export API_HOST_PORT=18101
export DB_HOST_PORT=55440
export DEFAULT_PROVIDER=ollama
export OPENROUTER_API_KEY=
export ANTHROPIC_API_KEY=
```

Use the README fetch, bootstrap, and ingestion commands with this environment. Poll with `python3 scripts/wait_ready.py --url http://127.0.0.1:18101/api/health/ready`; open `http://localhost:18100/workspace`. Restore the same project/port settings in a new terminal. These example ports are not an instruction to replace an existing workspace.

## Full ingestion and refresh

The quick start indexes three interviews. For the complete pinned snapshot, omit source filters:

```sh
python3 scripts/docker.py compose exec -T api python -m backend.ingest \
  --root "/corpus/$CORPUS_REVISION" --batch-size 4 --deadline-seconds 3600
```

Run one ingestion process at a time. Repeat the same command to resume; committed unchanged episodes skip. Snapshot verification must pass first. Reuse a verified snapshot by linking its complete cache directory before bootstrap, preserving its revision manifest. For a new corpus revision, fetch into a new immutable directory and verify its manifest. Never overwrite old source snapshots or fabricate timestamps.

Embedding model, digest, dimensions, and prefixes must match the stored index identity. Changing embeddings needs a deliberately separate index rebuild, not renaming existing vectors. Additive migrations run in the API before serving; do not edit applied migrations or downgrade normal data.

## Recovery and saved work

Inspect readiness, the saved run’s error code, and correlation ID before retrying. Keep the original question/request identity; completed requests replay and failed retries are explicit and bounded. An `rpc_rejected` error is not proof of insufficient evidence. [Troubleshooting](troubleshooting.md)

After active work finishes, verify restart/reopen on the intended isolated project:

```sh
python3 scripts/docker.py compose restart api web
python3 scripts/wait_ready.py --url "http://127.0.0.1:$API_HOST_PORT/api/health/ready"
```

Reopen the same session, citation, Markdown, and HTML. Compare saved content; readiness is not a live-answer pass. Do not restart services during a suite or model run.

## Extending the app

Use narrow schema-validated Pi tools and extend their policy tests. Keep keys server-side, cloud selection explicit, and fallback disabled. Treat transcript text as untrusted evidence; source IDs and exact spans are authoritative. Review support separately from citation existence.

Run [automated/manual checks](test-plan.md) with isolated test databases. Keep mock, database, browser, and live-model evidence distinct. The reviewed essay has nine disclosed edits; frozen acceptance remains 0/5. [Results](verification.md)
