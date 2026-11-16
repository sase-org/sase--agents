# Chat History - ace-run (sase-1t3.6.1.2)

- **TIMESTAMP:** 2026-11-16 13:17:09 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1t3.6.1.2

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1t3.6.1, bead=sase-1t3.6.1.2)
%model:@medium
%w(sase-1t3.6.1.1, for_epic=false)
%w(bead=sase-1t3.6.1.1)
Can you complete the work for bead sase-1t3.6.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1t3.6.1.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1t3.6.1.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1t3.6.1.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1t3.6.1.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1t3.6.1.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1t3.6.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1t3.6.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Build is running in the background monitor. Pausing here — verification (Python parity tests, `just check`, epic-symbols, bead close) resumes when the Rust wheel rebuild completes.
Work complete. Bead `sase-1t3.6.1.2` (named-bundles phase) is implemented and verified; close is blocked only by upstream `Justfile` rows that land must update (re-keyed to parent `sase-1t3.6.1`, noted on the bead for the land agent).

## What was built

**sase-core** (`sase/repos/linked/sase-core`):
- Archive store schema v3→v4: new `workflow_name` column, index, and projection through `summary_from_bundle`/`upsert`/`rebuild`/`delete`
- Name-or-workflow `UNION` query (one indexed branch per column, no `SCAN`, verified by query-plan test) matching the legacy `agent_name OR workflow_name` scan without substituting the `workflow` display field
- New `store_agent_names_match_workflow_name_projection` test; updated version assertions and representative test data
- All green: 16 store tests, 13 binding tests, 6014 lib tests, clippy/fmt clean

**sase**:
- [`_lookup_named.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/agent/names/_lookup_named.py): `find_named_agent` now uses `lookup_agent_artifacts` (exact name/workflow targets) plus archive-index bundle queries; only matching dirs are revalidated for liveness/outcome. Legacy ranking preserved (spelling order → live/dead/done → exact/workflow → timestamp; dismissed-prefix handling; per-spelling artifact-then-bundle fallback). Unusable indexes take the bounded 200-record fallback, never a full rebuild. Removed dead `ace_run_scan_options`.
- [`_models.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/ace/dismissed_bundle_index/_models.py): schema v4, optional `workflow_name` field
- [`Justfile`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/Justfile): consumed epic-symbol rows re-keyed from `sase-1t3.6.1.2` to parent `sase-1t3.6.1`; `epic-symbols` clean locally

**Tests**:
- New [`test_agent_names_indexed_lookup.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_agent_names_indexed_lookup.py): 9 parity + healthy-index regression tests (exact-vs-workflow, live/done, `only_done`/`include_dead`, root-only workflow, owner spellings, healthy miss, bundle fallback, bundle workflow-name, all visibilities) with `scan_agent_artifacts` and bundle `rglob` patched to fail
- Updated existing suites to build the artifact index before indexed lookups: `test_agent_names_lookup`, `test_chat_catalog`, `test_chat_handler_show`, `test_axe_run_agent_failed_fork_admission`
- 139 tests pass across named-lookup, dismissed-bundle, and lookup-wire suites; mypy/ruff/symvision clean; `sase tool run check` symvision gate passes

Pre-existing scoped failures (reproduce on clean tree: archive search CLI, TUI proof, gate retention, corpus facade) recorded as `PROPOSED FOLLOW-UP` notes on the bead; my regressions (chat/fork/show/catalog) fixed.## Bead `sase-1t3.6.1.2` (named-bundles): implementation complete, close blocked on upstream gate

All code, tests, and verification for the named-agent/dismissed-bundle indexed cutover are done. `sase bead close` refuses because `origin/master` still carries the three `--epic-symbol` rows; only land can clear upstream. Local tree has zero rows for this bead, symbols are consumed (symvision passes without allowlisting), and a `CLOSE-BLOCKED` note on the bead tells the land agent exactly what to do.

### sase-core changes

- **Archive store schema v3→v4** ([`store.rs`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/sase/repos/linked/sase-core/crates/sase_core/src/agent_archive/store.rs)): new `workflow_name` column + index, projected from bundle JSON in `summary_from_bundle`, written through `upsert`/`rebuild`, read in `summary_wire_from_row`.
- **Name-or-workflow lookup** ([`store.rs`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/sase/repos/linked/sase-core/crates/sase_core/src/agent_archive/store.rs)): `agent_names` filter matches `agent_name` OR `workflow_name` (never the display `workflow` field) via per-column `UNION` branches so each keeps its single-column index seek — no `SCAN`, proven by the query-plan test.
- **Wire** ([`wire.rs`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/sase/repos/linked/sase-core/crates/sase_core/src/agent_archive/wire.rs)): `DismissedBundleSummaryWire.workflow_name`.
- **Tests**: new `store_agent_names_match_workflow_name_projection` (agent match, workflow match, display-field exclusion); version assertions bumped to 4; background-row workflow data so the planner uses the index.
- **Results**: 16 store tests, 13 `agent_custody` binding tests, full `sase_core` lib suite (6014 passed), clippy/fmt clean.

### sase changes

- [`_lookup_named.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/agent/names/_lookup_named.py): `find_named_agent` now queries `lookup_agent_artifacts` (exact name/workflow targets, `include_hidden=True`) and ranks hits per spelling with legacy ordering (spelling order → live/dead/done → exact/workflow → timestamp; dismissed-prefix historical handling; non-root workflow exclusion; `only_done`/`include_dead`). Only matching dirs are touched on disk (liveness via `agent_meta.json`, outcome via `done.json`). Dismissed bundles resolve through the archive index (`agent_names`, all visibilities, children included), hydrating only the winning bundle file; unusable indexes take a bounded newest-first scan (200 files, no `rglob`).
- [`_lookup_artifacts.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/agent/names/_lookup_artifacts.py): removed dead `ace_run_scan_options` (sole consumer gone; symvision clean).
- [`_models.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/ace/dismissed_bundle_index/_models.py): schema v4, optional `workflow_name`.
- [`Justfile`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/Justfile): all three `sase-1t3.6.1.2` epic-symbol rows deleted locally (zero local references to the bead ID); symvision passes without them, proving consumption of `lookup_agent_artifacts`, `AgentArtifactLookupTargetWire`, `AgentArtifactLookupHitWire`.

### Tests

- New [`test_agent_names_indexed_lookup.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_agent_names_indexed_lookup.py): 9 tests covering exact-vs-workflow, live-vs-done, `only_done`/`include_dead`, root-only workflow, owner spellings, healthy miss, bundle fallback, bundle workflow-name, and all visibilities — with `scan_agent_artifacts` and bundle `rglob` patched to fail.
- Updated fixtures to build the artifact index before indexed lookups: `test_agent_names_lookup` (15 tests), `test_chat_catalog` (2), `test_chat_handler_show` (1), `test_axe_run_agent_failed_fork_admission` (3), plus the `workflow_name` field-set test.
- **139+ tests pass** across named-lookup, dismissed-bundle, chat, fork, and lookup-wire suites; mypy/ruff clean.

### Pre-existing failures (recorded as `PROPOSED FOLLOW-UP` on the bead)

Spot-checked on the clean tree: `test_agent_search_archive_cli`, TUI proof, gate retention, and corpus facade failures reproduce without my changes (untouched areas / parallel work). My regressions (chat, fork, show, catalog) were fixed.

### For the land agent

Landing this branch replaces upstream `sase-1t3.6.1.2(...)` rows with nothing (symbols consumed — verified by symvision passing with zero local rows). After landing, `sase bead epic-symbols sase-1t3.6.1.2` will be empty and the phase will close cleanly.

Declaration submitted: main commit closes sase-1t3.6.1.2, sase-core commit keeps it open.
