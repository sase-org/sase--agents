# Chat History - ace-run (toobig-53.artifact_link_outbox.0)

- **TIMESTAMP:** 2026-09-10 06:08:28 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-53.artifact_link_outbox.0

## Prompt

%wait:toobig-53.artifact_link_event_publisher.0
%id(artifact_link_outbox.0, clan=toobig-53)
%model:@medium
%auto
%queue(runners=3)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/sdd/artifact_link_outbox.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting `artifact_link_outbox.py` and the surrounding SDD layout so the split stays under 500 lines without changing behavior.

The file is 936 lines. I'll read the rest of it and map its public surface so the split can preserve imports.

I'll check tests, patch targets, and split conventions so private names and monkeypatches keep working.

I’ll split along the existing private-module pattern: types, JSONL I/O, apply, drain, plus a thin public facade.

I'll format first, then lint the new modules so obvious issues are fixed before the full check.

Targeted lint and tests passed. Next I’ll run the repo `just check` gate.

Split `src/sase/sdd/artifact_link_outbox.py` (936 lines) the same way as the event-publisher and publication-retry modules: a thin public facade plus private siblings.

`artifact_link_outbox.py` is still the public import path (`append_*`, `drain_*`, `inspect_*`, filenames, schema version). Callers did not need to change.

| File | Role | Lines |
|---|---|---|
| `artifact_link_outbox.py` | Public re-exports | 27 |
| `_artifact_link_outbox_types.py` | Queue records, JSON parse, row/event helpers | 251 |
| `_artifact_link_outbox_io.py` | JSONL append/read/rewrite/inspect | 256 |
| `_artifact_link_outbox_apply.py` | Converge queued rows and upsert sidecar indexes | 146 |
| `_artifact_link_outbox_drain.py` | Drain orchestration, partitions, eligibility | 364 |

Tests that used `_read_artifact_link_outbox_entries` now import `read_artifact_link_outbox_entries` from the IO module. The eligibility monkeypatch points at `_artifact_link_outbox_drain._entry_is_eligible`.

`just check` passed, including the scoped suite (it escalated to the full suite for this change).
