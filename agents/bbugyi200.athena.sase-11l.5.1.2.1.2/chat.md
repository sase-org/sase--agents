# Chat History - ace-run (sase-11l.5.1.2.1.2)

- **TIMESTAMP:** 2026-09-17 07:31:38 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-11l.5.1.2.1.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-11l.5.1.2.1, bead=sase-11l.5.1.2.1.2)
%model:@medium
%auto
%w:sase-11l.5.1.2.1.1
%w(bead=sase-11l.5.1.2.1.1)
Can you complete the work for bead sase-11l.5.1.2.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-11l.5.1.2.1.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-11l.5.1.2.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-11l.5.1.2.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's description and design file.

This is the "hold-facade" phase (§5 of the plan). Let me explore the current state of the relevant files before making changes.

Good — the Rust bindings (`agent_hold_rebind`, `launch_unit_hold_key`, `launch_unit_hold_armer`) already exist and match the pin. Now let's look at the current facade and related files in detail.

Now let's check `agent_hold_pending.py`, config getters, `runner_slots` package, and `rust.py` for `require_rust_binding`.

Now let's check `runner_slots` package for `DEFAULT_WAIT_PRIORITY` and `_admission_types.py`.

Good, matches spec exactly. Let's check `launch_unit_hold_armer` and `agent_hold_rebind` signatures similarly, plus inspect an existing agent-kind armer dict shape and how `AgentLaunchWire`/unit JSON looks (to build the `unit` dict argument correctly).

Now let's look at the existing `test_agent_hold_service.py` to understand test conventions before I extend it, and check `agent_hold_notifications.py` briefly for `upsert_hold_armed_notification` signature (used unchanged).

Good, that confirms tests get an isolated SASE_HOME automatically. Now let's check `tests/_runner_slot_fixtures.py`'s `artifact()` helper and check `sase.core.agent_artifact_paths.parse_agent_artifact_path` briefly, plus look at `launch_admission_engine_holds.py` (already exists, related to sase-11l.7 proc hold candidates).

Now I have enough context. Let's implement the changes, starting with `agent_hold_store.py`.

Now update `agent_hold_liveness.py` to add the `launch` liveness fact:

Now let's update `agent_hold_facade.py`: rename `_agent_armer_wire`, add `rebind_agent_hold`, `resolve_hold_ttl_seconds`, and extend `arm_agent_hold`.

Confirmed pre-existing, not something I introduced. Continuing with `arm_agent_hold`, `rebind_agent_hold`, and `resolve_hold_ttl_seconds`.

Now let's add `rebind_agent_hold` and `resolve_hold_ttl_seconds`, right after `release_agent_hold`.

Now update `__all__`:

Now update the audit test file's dict key for the renamed function.

Now let's update `_admission_types.py` and `runner_slots/__init__.py` for `HOLD_ARMER_WAIT_PRIORITY`.

Now let's create `src/sase/agent/launch_hold.py`.

Only used in `_resolve_ttl_seconds`. Let's update the CLI file now.

Now remove the now-unused `_format_seconds` helper and add "Done marker:" rendering to `_print_hold_detail`.

Now add "Done marker:" to `_print_hold_detail`.

Good, that looks correct. Now let's write/extend tests. First, let's write tests for `launch_hold.py` primitives (new file) and extend `test_agent_hold_service.py`. Let's check `_runner_slot_fixtures.py`'s `artifact` helper signature to build test fixtures for the launch liveness fact.

All scenarios behave exactly as specified. Now let's write the tests. First, extend `tests/test_agent_hold_service.py`.

Expected — will resolve once tests are added. Let's view the section around line 99-110 to insert the pid-fallback test after the artifacts-dir test.

Now let's add tests for `arm_agent_hold` with explicit `armer`/`selectors`, kin rejection, `resolve_hold_ttl_seconds`, and `rebind_agent_hold` at the end of the file.

Good, confirmed. Now let's append all these tests to the file.

Good, generic and kind-agnostic — no issue. Now let's run these new/edited tests to check correctness.

All 31 tests pass. Now let's add "launch" kind liveness/validation tests as a separate test grouping — I'll add a small dedicated test class section within the same file for clarity, matching spec bullets.

All 37 pass. Now let's write `tests/test_launch_hold.py` for the new primitives module.

Confirms it's a real Python import (works fine); the pyright warning is just cache lag for the newly created file. Let's re-check diagnostics after a brief pause by touching a trivial edit-verify cycle, or just proceed — it should clear once pyright re-scans. Let's verify with a quick lint/typecheck run instead.

Confirmed clean — that was just editor cache lag. Now let's check the memory note about lint/test procedure since files changed.

Let's continue watching `just fix` finish, then check the diff of the modified files for unexpected formatting changes.

Good, that's exactly my intended change (formatting-neutral). Now let's run `just check`.

Good, `sase-11l.5.1.2.1` is IN_PROGRESS. Let's find the Justfile's symvision invocation to see the existing `--epic-symbol` pattern.

Let's look at `src/sase/bead/epic_symbols.py` for the exact regex/format expected, and how `sase bead epic-symbols` parses the Justfile.

Symvision passes now. Let's rerun `just check` in full.

Confirmed — those diagnostics are in pre-existing lines untouched by my diff (already existed before). Good, unrelated. Now let's run the full lint check again quickly (mypy/ruff) plus the broader hold test suite for regressions.

All clean. Now let's run the broader hold-related and runner-slot test files to check for regressions from the `HOLD_ARMER_WAIT_PRIORITY` addition and other touched modules.

All pass. Now let's check `runner_slots` test coverage for the new `HOLD_ARMER_WAIT_PRIORITY` export.

Good, confirms `priority <= DEFAULT_WAIT_PRIORITY` → 0.0 deference. Let's add a small test.

Pre-existing unrelated lines again. Let's run `just fix` once more and re-run the full lint + this targeted test slice to confirm everything's still green before finalizing.

Good, no reformatting churn. Let's run the full `just check` one more time to get a clean confirmation (accepting the one known pre-existing failure).

Confirmed — the only failure is the pre-existing, unrelated `test_proc_env_isolation` test. All lint gates and 42,477 other tests pass. Now let's file the PROPOSED FOLLOW-UP note and close the bead.

Now let's re-verify epic-symbols one final time and close the bead.

Final declaration accepted with `bead_action: "keep"` (the bead was already closed directly via `sase bead close`, per the task's explicit instructions, before this commit-only finalization step).

## Summary

Completed bead **sase-11l.5.1.2.1.2** (Python hold facade and launch-hold primitives, plan §5):

- **`agent_hold_facade.py`**: renamed `_agent_armer_wire` → public `agent_armer_wire_for_artifacts(pid_fallback=)`; `arm_agent_hold` gained `armer`/`selectors` overrides (pending merges into `selectors["artifact_dirs"]`, dropping the armer's own artifacts dir); added `rebind_agent_hold` and `resolve_hold_ttl_seconds`.
- **`agent_hold_store.py`** / **`agent_hold_liveness.py`**: accept and evaluate the new `launch` armer kind (pid-alive via `started.json` fallback, `done_marker_present` treats `receipt.json` specially — only `complete: true` counts).
- **`cli_hold.py`**: `_resolve_ttl_seconds` now delegates default/cap logic to the facade (unchanged error text); hold detail view prints `Done marker:`.
- **New `src/sase/agent/launch_hold.py`**: key/armer/arm/rebind/release primitives plus `LaunchHoldError`, with no call sites yet (later phases wire them up).
- **`core/runner_slots`**: added `HOLD_ARMER_WAIT_PRIORITY = 5`.
- Added/extended tests across `test_agent_hold_service.py`, new `test_launch_hold.py`, `test_agents_hold_handler.py`, `test_runner_slots_priority.py`.
- Whitelisted the not-yet-consumed public symbols via 9 `--epic-symbol` Justfile entries keyed to the still-open parent epic `sase-11l.5.1.2.1`.

`just check` is green aside from one pre-existing, unrelated failure (`test_proc_env_isolation.py`, caused by an earlier commit's test-file split) — filed as a `PROPOSED FOLLOW-UP` note on the bead for the epic's land agent to triage.
