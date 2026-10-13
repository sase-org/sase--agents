# Chat History - ace-run (sase-1jm.9.3--2)

- **TIMESTAMP:** 2026-10-12 19:08:25 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1jm.9.3--2

## Prompt

%queue(weight=1)
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:570039780f55be886db0b4b7507771e5`

- **Node:** `agent-delta:20261012181922:a41ce533fc4f63c4`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261012181922:a41ce533fc4f63c4.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-2347fd159c8be3db.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%queue(weight=1)
% macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:614fbe5a8c9d042edd56a8b42b2fe82e`

- **Node:** `agent-delta:20261012145229:37a5662b45edf140`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261012145229:37a5662b45edf140.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-f35bf6cfc5362984.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

#gh:gh_sase-org__sase
%id(3, clan=sase-1jm.9, bead=sase-1jm.9.3)
%model:@medium
%auto
%w(sase-1jm.9.1, for_epic=false)
%w(bead=sase-1jm.9.1)
Can you complete the work for bead sase-1jm.9.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1jm.9.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1jm.9.3 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1jm.9.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1jm.9.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase: budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-f35bf6cfc5362984.json;covered=agent-delta%3A20261012145229%3A37a5662b45edf140-->
# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: xv8zmgzhpjze
Inspect with: sase monitor show xv8zmgzhpjze
Monitor turn: sase-1jm.9.3--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14

Command:

```sh
just fix-tui-screenshots -- -k test_archive_chooser
```

Reason:

Capture Archive chooser PNG goldens for sase-1jm.9.3

Next action:

Continue bead sase-1jm.9.3 (phase archive-chooser-copy). The bead is already reserved and in_progress for this agent; do not set status by hand. Do not close the parent epic sase-1jm.9 or any ancestor. Do not create beads; record leftover as `sase bead note sase-1jm.9.3 'PROPOSED FOLLOW-UP: …'`. Honor the epic DECISIONS (final). Do not regenerate help-modal goldens (`test_ace_png_snapshots_help_panel.py` or the Archive help capture in `test_ace_png_snapshots_agents_archive.py`).

## What the previous agent finished

Production is in the tree: Archive chooser READ section (Open chat / y / %); container Enter opens the chooser with `Restore clan|session <label> (N members)` (`l`/`h` still expand/collapse); marks offer Restore N even when the cursor is unrestorable or unreadable; Fork requires a retained chat; hydrate off the event loop via `_archive_run_off_thread` / `asyncio.to_thread` + `_archive_spawn` / `spawn_pump_free_task`, with sync fallback when no loop; chooser callbacks use the captured hydrated agent; dedicated `agents_copy_reference` on `y` (tab-disjoint from `artifacts_copy_reference`); `%l` uses `format_markdown_link(f"@{reference}", reference)` with no doubled `agent:`; `%j` copies archive bundle JSON off-thread even without a hydrated agent, metadata JSON in Inbox; help Copy Mode lists `%!` `%l` `%j` `%d` `y`; docs in `docs/ace.md` and `docs/configuration.md`. Footer restore chip is unchanged.

Targeted unit tests passed after fixing `test_artifacts_copy_reference_on_artifacts_tab` to set `current_artifacts_subtab` (the clipboard mixin exposes `current_artifacts_pane_key` as a property). `just fmt` was clean. `sase bead epic-symbols sase-1jm.9.3` reported no leftovers — re-run before close.

## This monitor

It ran `just fix-tui-screenshots -- -k test_archive_chooser` to create:
- `agents_archive_chooser_120x40` (ARCHIVE then READ, Restore to inbox)
- `agents_archive_chooser_marked_120x40` (Restore 2 marked)

## Your job

1. Inspect the visual report before treating goldens as approved. Generation is not approval.
   - Read `.pytest_cache/sase-visual/latest-report.json` (and the run dir it points at).
   - If status is `partial`, read the WARNING block / `skipped` list / `pruning_skipped_reason`; those goldens are unchanged and not known to be current.
   - Inspect every creation and removal, then each update group. Expand unexpected diffs.
   - Expected: CREATED the two chooser goldens. Reject unexpected help-modal or unrelated Archive golden updates unless they are genuine fallout of this phase (they should not be).
   - Open both PNGs and confirm ARCHIVE + READ headings, Restore to inbox vs Restore 2 marked, and the read rows (Open chat, Copy, More copy).
   - If capture failed, fix the visual tests in `tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py` and recapture only those two selectors through `/sase_monitor`. Do not recapture help-modal goldens.

2. After goldens look correct, verify and close:
   - Run `just fmt` (or `just fix`) if you edited anything.
   - Re-run `sase bead epic-symbols sase-1jm.9.3`. If this phase still has `--epic-symbol` entries, resolve each or re-key the Justfile line to a still-open bead. Close refuses while leftovers remain.
   - Prefer prepared host completion: `sase final context -f json`, build a wrapper with `bead_action: "close"` on the primary repo, `sase final prepare <wrapper> -j`, then `sase monitor start -p verify -f <ref> -r 'Verify archive-chooser-copy before host completion' -- just check`. The monitored argv must exactly match the intent's verification command.
   - If prepare is refused, run `sase tool run check` inline (never `just check-full`). If it escalates (exit 124), join with `sase monitor start -J <run-id> -p verify -n '…'` using the exact run id. Do not wrap in timeout.
   - Known check failures that reproduce identically on the clean base tree do not keep this bead open: record `PROPOSED FOLLOW-UP:` citing existing owners (`sase-1ic` import budget, `sase-1k4` Project: fake/tmp header tests, `sase-1jx` New Project symvision, `sase-1kd` plan decision-card symvision) and close anyway.

3. Close only this bead:
   `sase bead close sase-1jm.9.3 --note "<what you verified>"`
   Note should cover: READ section; container Enter Restore clan/session; marks; Fork gated on retained chat; off-loop hydrate; `agents_copy_reference` y; `%l`/`%j`; help/docs; chooser goldens inspected; `sase tool run check` result; epic-symbols clean.

4. Submit `/sase_final` as the last action. Include the new PNG goldens in the commit. Do not invoke `/sase_git_commit`.
<!--sase: budget-span:close:1-->

---

% macros_enabled:true
# New Query
%model:grok-4.6@high

% macros_enabled:false
# Monitored command finished

**Command:**

```text
just fix-tui-screenshots -- -k test_archive_chooser
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-10-12T22:15:02.429345+00:00 |
| **Finished** | 2026-10-12T22:17:43.541252Z |
| **Elapsed** | 2m 39s of a 45m 0s budget |
| **Output** | 9 KiB · evidence refs: `file:monitor-diagnostic-manifest:xv8zmgzhpjze`, `file:monitor-retained-log:xv8zmgzhpjze` · raw output omitted: `facts_only` · full log: `sase monitor show xv8zmgzhpjze --all-lines` |
| **Tool run** | sase tool show f718418f7844472f32b43f03e58b2520 |

**Why this was monitored:** Capture Archive chooser PNG goldens for sase-1jm.9.3

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-4eff5ee6e2c687f5.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "just fix-tui-screenshots -- -k test_archive_chooser",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14",
    "member_agent_name": "sase-1jm.9.3--mon",
    "monitor_id": "xv8zmgzhpjze",
    "next_output": "auto",
    "parent_node_ids": [],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:ace1b32f432e29156e6ee686e3b8e7ff4ea392ba82b53ea7fc66f72b89d0efd1",
    "starter_agent": "sase-1jm.9.3--plan",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202610/12/20261012145229"
  },
  "recorded_at_epoch": 1791843303.9116004,
  "schema_version": 1
}
```


## Your next action

Continue bead sase-1jm.9.3 (phase archive-chooser-copy). The bead is already reserved and in_progress for this agent; do not set status by hand. Do not close the parent epic sase-1jm.9 or any ancestor. Do not create beads; record leftover as `sase bead note sase-1jm.9.3 'PROPOSED FOLLOW-UP: …'`. Honor the epic DECISIONS (final). Do not regenerate help-modal goldens (`test_ace_png_snapshots_help_panel.py` or the Archive help capture in `test_ace_png_snapshots_agents_archive.py`).

## What the previous agent finished

Production is in the tree: Archive chooser READ section (Open chat / y / %); container Enter opens the chooser with `Restore clan|session <label> (N members)` (`l`/`h` still expand/collapse); marks offer Restore N even when the cursor is unrestorable or unreadable; Fork requires a retained chat; hydrate off the event loop via `_archive_run_off_thread` / `asyncio.to_thread` + `_archive_spawn` / `spawn_pump_free_task`, with sync fallback when no loop; chooser callbacks use the captured hydrated agent; dedicated `agents_copy_reference` on `y` (tab-disjoint from `artifacts_copy_reference`); `%l` uses `format_markdown_link(f"@{reference}", reference)` with no doubled `agent:`; `%j` copies archive bundle JSON off-thread even without a hydrated agent, metadata JSON in Inbox; help Copy Mode lists `%!` `%l` `%j` `%d` `y`; docs in `docs/ace.md` and `docs/configuration.md`. Footer restore chip is unchanged.

Targeted unit tests passed after fixing `test_artifacts_copy_reference_on_artifacts_tab` to set `current_artifacts_subtab` (the clipboard mixin exposes `current_artifacts_pane_key` as a property). `just fmt` was clean. `sase bead epic-symbols sase-1jm.9.3` reported no leftovers — re-run before close.

## This monitor

It ran `just fix-tui-screenshots -- -k test_archive_chooser` to create:
- `agents_archive_chooser_120x40` (ARCHIVE then READ, Restore to inbox)
- `agents_archive_chooser_marked_120x40` (Restore 2 marked)

## Your job

1. Inspect the visual report before treating goldens as approved. Generation is not approval.
   - Read `.pytest_cache/sase-visual/latest-report.json` (and the run dir it points at).
   - If status is `partial`, read the WARNING block / `skipped` list / `pruning_skipped_reason`; those goldens are unchanged and not known to be current.
   - Inspect every creation and removal, then each update group. Expand unexpected diffs.
   - Expected: CREATED the two chooser goldens. Reject unexpected help-modal or unrelated Archive golden updates unless they are genuine fallout of this phase (they should not be).
   - Open both PNGs and confirm ARCHIVE + READ headings, Restore to inbox vs Restore 2 marked, and the read rows (Open chat, Copy, More copy).
   - If capture failed, fix the visual tests in `tests/ace/tui/visual/test_ace_png_snapshots_agents_archive.py` and recapture only those two selectors through `/sase_monitor`. Do not recapture help-modal goldens.

2. After goldens look correct, verify and close:
   - Run `just fmt` (or `just fix`) if you edited anything.
   - Re-run `sase bead epic-symbols sase-1jm.9.3`. If this phase still has `--epic-symbol` entries, resolve each or re-key the Justfile line to a still-open bead. Close refuses while leftovers remain.
   - Prefer prepared host completion: `sase final context -f json`, build a wrapper with `bead_action: "close"` on the primary repo, `sase final prepare <wrapper> -j`, then `sase monitor start -p verify -f <ref> -r 'Verify archive-chooser-copy before host completion' -- just check`. The monitored argv must exactly match the intent's verification command.
   - If prepare is refused, run `sase tool run check` inline (never `just check-full`). If it escalates (exit 124), join with `sase monitor start -J <run-id> -p verify -n '…'` using the exact run id. Do not wrap in timeout.
   - Known check failures that reproduce identically on the clean base tree do not keep this bead open: record `PROPOSED FOLLOW-UP:` citing existing owners (`sase-1ic` import budget, `sase-1k4` Project: fake/tmp header tests, `sase-1jx` New Project symvision, `sase-1kd` plan decision-card symvision) and close anyway.

3. Close only this bead:
   `sase bead close sase-1jm.9.3 --note "<what you verified>"`
   Note should cover: READ section; container Enter Restore clan/session; marks; Fork gated on retained chat; off-loop hydrate; `agents_copy_reference` y; `%l`/`%j`; help/docs; chooser goldens inspected; `sase tool run check` result; epic-symbols clean.

4. Submit `/sase_final` as the last action. Include the new PNG goldens in the commit. Do not invoke `/sase_git_commit`.
% macros_enabled:true

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase:budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-2347fd159c8be3db.json;covered=agent-delta%3A20261012181922%3Aa41ce533fc4f63c4-->
# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: rbsaj5ck81k2
Inspect with: sase monitor show rbsaj5ck81k2
Monitor turn: sase-1jm.9.3--mon-0
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14

Command:

```sh
just check
```

Reason:

Verify archive-chooser-copy before host completion
<!--sase:budget-span:close:1-->

---

%macros_enabled:true
# New Query
%model:grok-4.6@high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-12T22:26:59.530128+00:00 |
| **Finished** | 2026-10-12T22:51:53.645035Z |
| **Elapsed** | 24m 53s of a 1h 0m 0s budget |
| **Output** | 181 KiB · evidence refs: `file:monitor-diagnostic-manifest:rbsaj5ck81k2`, `file:monitor-retained-log:rbsaj5ck81k2`, `file:monitor-stage:test-scoped-2699696-1791845510813210513-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show rbsaj5ck81k2 --all-lines` |
| **Tool run** | sase tool show c0fe2ba749f88adc38ec1224335470b7 |

**Why this was monitored:** Verify archive-chooser-copy before host completion

## Failure triage

verdict: new_failures — 1 NEW, 10 KNOWN; exit 1

NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_jump_panel_prefix.py::test_neighbors_map_shows_dismissed_revive_cells - AssertionError: assert 'revive' in '⊘ 1 lane.old ▶ archive' — recorded evidence; no owner
KNOWN 10; FLAKY 0

sase tool show c0fe2ba749f88adc38ec1224335470b7 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== test (scoped) (failed exit 1) ==
[counts: output_bytes=130472, output_lines=1572, retained_bytes=130472]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.39.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed, src-data-asset); 5171 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, platformdirs-4.12.4, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 12/12 workers
12 workers [55385 items]

........................................................................ [  0%]
........................................................................ [  0%]
......................................................s................. [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
..............................................s......................... [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
..................................................................

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true

## Response

The `just check` monitor failed with one new test. I'll inspect that failure, the visual goldens, and the bead scope, then repair and close.

Visual report is applied with two records and no skips. Next I’ll pull the bead, the failing test, and the golden PNGs.

The visual run created exactly the two chooser goldens. Next I’ll inspect those PNGs, the new test failure, and the epic DECISIONS.

Chooser goldens look right. I’ll inspect the new jump-panel failure and whether this phase’s archive work caused it.

Goldens match the spec. The new failure looks like a stale “revive” assertion under `jump_opens_archive`; I’ll confirm it against clean HEAD and the jump-panel renderer.

The jump-panel test fails the same way on clean HEAD, so it is not this phase. I’ll restore the stash if needed, search for an owner, then close.

The stash never came back — the working tree is clean. Restoring it now.

Epic-symbols are clean. The new jump-panel assertion fails on clean HEAD (same leftover as KNOWN `test_dismissed_marker`). I’ll record that follow-up, close the phase, and submit.

Phase tests passed. Next I’ll record the follow-up, close the bead, and submit the host finalizer.

Bead is closed. I’ll submit the host commit with `bead_action: close` so the new chooser goldens land.

Phase `sase-1jm.9.3` is complete and closed. The host will commit the Archive chooser work after this turn.

Chooser goldens were inspected and match the spec. Visual report status was `applied` with `created=2`, `skipped=0`, and no unrelated updates:

- `agents_archive_chooser_120x40` — ARCHIVE then READ, **Restore to inbox**, Open chat / Copy / More copy
- `agents_archive_chooser_marked_120x40` — same layout with **Restore 2 marked**

`just check` (`c0fe2ba749f88adc38ec1224335470b7`) had 1 NEW failure that is outside this phase: `test_neighbors_map_shows_dismissed_revive_cells` still expects `revive` while production shows `▶ archive` (`jump_opens_archive=yes`). It fails the same way on clean HEAD `c4d84f9a1a`, same leftover as KNOWN `test_dismissed_marker`. Recorded as `PROPOSED FOLLOW-UP` (also noted earlier on `sase-1jx.13.5`; no task bead yet). The other 10 failures are KNOWN (`sase-1ic` import budget, `sase-1k4` Project header tests, plus node-finder / archive parking / source-groups / path-label).

52 phase unit tests passed. `sase bead epic-symbols sase-1jm.9.3` was clean. Parent epic `sase-1jm.9` was left open.
