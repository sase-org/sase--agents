# Chat History - ace-run (toobig-8u.declaration.0--2)

- **TIMESTAMP:** 2026-10-30 04:40:10 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8u.declaration.0--2

## Prompt

%queue(weight=1)
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:849809f9be83ea255eb77d823e1421f0`

- **Node:** `agent-delta:20261030035908:087f201452bd98e0`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261030035908:087f201452bd98e0.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-bb31ff41f10f9b84.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%queue(weight=1)
% macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:312791ceb7c7765dbf8b51d67576cad7`

- **Node:** `agent-delta:20261029184912:6579d4f480ad67b4`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261029184912:6579d4f480ad67b4.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-2ff71fb159d06ff8.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%auto
%id(declaration.0, clan=toobig-8u)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/finalizers/declaration.py` file into multiple files? Use your best
%wait:toobig-8u.run_agent_exec_staged.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase: budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-2ff71fb159d06ff8.json;covered=agent-delta%3A20261029184912%3A6579d4f480ad67b4-->
# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: h34t43gdk4mq
Inspect with: sase monitor show h34t43gdk4mq
Monitor turn: toobig-8u.declaration.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22

Command:

```sh
sase tool run -k check
```

Reason:

Re-run the requested check after fixing the declaration dirty-state seam

Next action:

Inspect the ToolRun result. The declaration dirty-state monkeypatch seam is now a private one-argument wrapper named _collect_dirty_state in _declaration_context.py; previous failures came from retargeting tests to the lower-level collector. Fix any remaining failures in split-touched files, rerun the requested lints individually if code changes, then use /sase_final. Symvision is currently blocked by stale Justfile epic-symbol entries for closed bead sase-1pu.5.1.3; Justfile has been restored and this issue is unrelated.
<!--sase: budget-span:close:1-->

---

% macros_enabled:true
# New Query
%model:gpt-6-luna@xhigh

% macros_enabled:false
# Monitored command finished

**Command:**

```text
sase tool run -k check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-30T07:41:06.498430+00:00 |
| **Finished** | 2026-10-30T07:58:25.541037Z |
| **Elapsed** | 17m 17s of a 45m 0s budget |
| **Output** | 28 KiB · evidence refs: `file:monitor-diagnostic-manifest:h34t43gdk4mq`, `file:monitor-retained-log:h34t43gdk4mq`, `file:monitor-stage:lint-symvision-1383057-1793346433980129015-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show h34t43gdk4mq --all-lines` |

**Why this was monitored:** Re-run the requested check after fixing the declaration dirty-state seam

## Failure triage

verdict: new_failures — 3 NEW; exit 1

NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show d265ad245595e085b76d3c0f79edac91 -j

## Selected diagnostics

<!--sase: budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=3264, output_lines=10, retained_bytes=3264]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1pj.5.1.2(staged_monitor_launch_payload_schema_version)' --epic-symbol 'sase-1pj.5.1.2(validate_staged_monitor_launch_payload)' --epic-symbol 'sase-1pj.5.1.2(evaluate_staged_monitor_membership)' --epic-symbol 'sase-1pj.5.1.2(evaluate_staged_owner_liveness)' --epic-symbol 'sase-1pj.5.1.2(tool_run_reserve_staged_join)' --epic-symbol 'sase-1pj.5.1.2(tool_run_activate_staged_join)' --epic-symbol 'sase-1pj.5.1.2(tool_run_release_staged_join)' --epic-symbol 'sase-1pj.5.1.3(reserve_prepared_intent)' --epic-symbol 'sase-1pj.5.1.3(release_prepared_intent)' --epic-symbol 'sase-1pj.5.1.3(load_prepared_intent_reservations)' --epic-symbol 'sase-1pj.5.1.4(evaluate_staged_self_wait)' --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)' --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)' --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)' --epic-symbol 'sase-1pu.5.1.4(advance_agent_run_state_schedule)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectIdentityWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateScheduleOutcomeWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectCheckpointWire)' --epic-symbol 'sase-1pj.4.1.6(WorkflowCompletionError)' --epic-symbol 'sase-1pj.4.1.6(WorkflowReviewIdentity)' --epic-symbol 'sase-1pj.4.1.6(PreparedWorkflowReview)' --epic-symbol 'sase-1pj.4.1.6(invoke_provider_for_review)' --epic-symbol 'sase-1pj.4.1.6(prepare_workflow_review)' --epic-symbol 'sase-1pj.4.1.6(complete_workflow_review)' 
Error: --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 522 with exit code 1

```

<!--sase: budget-span:close:1-->

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-8a206f93d1fb91b6.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "sase tool run -k check",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22",
    "member_agent_name": "toobig-8u.declaration.0--mon",
    "monitor_id": "h34t43gdk4mq",
    "next_output": "auto",
    "parent_node_ids": [],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:4c061f4dc106301b58664e3b630173ef9ce20b14b8cbf31ab25af1115c5135da",
    "starter_agent": "toobig-8u.declaration.0--plan",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202610/29/20261029184912"
  },
  "recorded_at_epoch": 1793346068.4891453,
  "schema_version": 1
}
```


## Your next action

Inspect the ToolRun result. The declaration dirty-state monkeypatch seam is now a private one-argument wrapper named _collect_dirty_state in _declaration_context.py; previous failures came from retargeting tests to the lower-level collector. Fix any remaining failures in split-touched files, rerun the requested lints individually if code changes, then use /sase_final. Symvision is currently blocked by stale Justfile epic-symbol entries for closed bead sase-1pu.5.1.3; Justfile has been restored and this issue is unrelated.
% macros_enabled:true

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase:budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-bb31ff41f10f9b84.json;covered=agent-delta%3A20261030035908%3A087f201452bd98e0-->
# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: 2bkwa81nctwj
Inspect with: sase monitor show 2bkwa81nctwj
Monitor turn: toobig-8u.declaration.0--mon-0
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22

Command:

```sh
sase tool run check
```

Reason:

Run the requested final check after the declaration split adjustments

Next action:

Inspect the ToolRun result. Fix any remaining failure in split-touched files, rerunning just _lint-symvision, just _lint-mypy, and just _lint-toobig individually if code changes. The known closed-bead epic-symbol failures in Justfile are unrelated to this split; leave Justfile untouched. Then use /sase_final.
<!--sase:budget-span:close:1-->

---

%macros_enabled:true
# New Query
%model:@medium

%macros_enabled:false
# Monitored command finished

**Command:**

```text
sase tool run check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-30T08:14:53.425946+00:00 |
| **Finished** | 2026-10-30T08:19:47.527072Z |
| **Elapsed** | 4m 49s of a 45m 0s budget |
| **Output** | 8 KiB · evidence refs: `file:monitor-diagnostic-manifest:2bkwa81nctwj`, `file:monitor-retained-log:2bkwa81nctwj`, `file:monitor-stage:lint-symvision-2153570-1793348385914922876-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 2bkwa81nctwj --all-lines` |
| **Tool run** | sase tool show b045617544fe588f24a83f38483d7c1e |

**Why this was monitored:** Run the requested final check after the declaration split adjustments

## Failure triage

verdict: new_failures — 9 NEW; exit 1

NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(WorkflowReviewIdentity)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(complete_workflow_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(prepare_workflow_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(WorkflowCompletionError)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(PreparedWorkflowReview)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.4.1.6(invoke_provider_for_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show b045617544fe588f24a83f38483d7c1e -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=4226, output_lines=16, retained_bytes=4226]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1pj.5.1.2(staged_monitor_launch_payload_schema_version)' --epic-symbol 'sase-1pj.5.1.2(validate_staged_monitor_launch_payload)' --epic-symbol 'sase-1pj.5.1.2(evaluate_staged_monitor_membership)' --epic-symbol 'sase-1pj.5.1.2(evaluate_staged_owner_liveness)' --epic-symbol 'sase-1pj.5.1.2(tool_run_reserve_staged_join)' --epic-symbol 'sase-1pj.5.1.2(tool_run_activate_staged_join)' --epic-symbol 'sase-1pj.5.1.2(tool_run_release_staged_join)' --epic-symbol 'sase-1pj.5.1.3(reserve_prepared_intent)' --epic-symbol 'sase-1pj.5.1.3(release_prepared_intent)' --epic-symbol 'sase-1pj.5.1.3(load_prepared_intent_reservations)' --epic-symbol 'sase-1pj.5.1.4(evaluate_staged_self_wait)' --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)' --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)' --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)' --epic-symbol 'sase-1pu.5.1.4(advance_agent_run_state_schedule)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectIdentityWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateScheduleOutcomeWire)' --epic-symbol 'sase-1pu.5.1.4(AgentRunStateProjectCheckpointWire)' --epic-symbol 'sase-1pj.4.1.6(WorkflowCompletionError)' --epic-symbol 'sase-1pj.4.1.6(WorkflowReviewIdentity)' --epic-symbol 'sase-1pj.4.1.6(PreparedWorkflowReview)' --epic-symbol 'sase-1pj.4.1.6(invoke_provider_for_review)' --epic-symbol 'sase-1pj.4.1.6(prepare_workflow_review)' --epic-symbol 'sase-1pj.4.1.6(complete_workflow_review)' 
Error: --epic-symbol 'sase-1pu.5.1.3(select_agent_run_state_window)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pu.5.1.3(AgentRunStateWindowRowWire)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pu.5.1.3(agent_run_state_wire_schema_version)': bead 'sase-1pu.5.1.3' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(WorkflowCompletionError)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(WorkflowReviewIdentity)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(PreparedWorkflowReview)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(invoke_provider_for_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(prepare_workflow_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.4.1.6(complete_workflow_review)': bead 'sase-1pj.4.1.6' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 522 with exit code 1

```

<!--sase:budget-span:close:1-->

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-eacc244516dfc51e.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "sase tool run check",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22",
    "member_agent_name": "toobig-8u.declaration.0--mon-0",
    "monitor_id": "2bkwa81nctwj",
    "next_output": "auto",
    "parent_node_ids": [],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:7dcb4795b985b2cf89bde9a80662682645346383bfabe4ef062ac739c9cd4762",
    "starter_agent": "toobig-8u.declaration.0--1",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202610/30/20261030035908"
  },
  "recorded_at_epoch": 1793348098.134898,
  "schema_version": 1
}
```


## Your next action

Inspect the ToolRun result. Fix any remaining failure in split-touched files, rerunning just _lint-symvision, just _lint-mypy, and just _lint-toobig individually if code changes. The known closed-bead epic-symbol failures in Justfile are unrelated to this split; leave Justfile untouched. Then use /sase_final.
%macros_enabled:true

## Response

Split is complete and verified.

- [declaration.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/finalizers/declaration.py) is now 450 lines (was 774), facade with identical `__all__`.
- [\_declaration_context.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/finalizers/_declaration_context.py) (286 lines) holds `LiveFinalizerContext`, `FinalContextPublication`, `build_live_context` plus private `_collect_dirty_state` seam.
- [\_declaration_carry.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/finalizers/_declaration_carry.py) (88 lines) holds `synthesize_carry_declaration`.
- No `_`-prefixed imports across new modules. Tests retargeted to `sase.finalizers._declaration_context._collect_dirty_state` and `sase.finalizers.declaration.build_live_context`.

Verification observed:

- `just _lint-toobig`: pass.
- `just _lint-mypy`: pass, no issues in 6219 files.
- `just _lint-symvision`: fails only on stale `Justfile` `--epic-symbol` entries for closed beads `sase-1pj.5.1.2`, `sase-1pu.5.1.3`, `sase-1pj.4.1.6`. No symvision errors in split-touched files. Left `Justfile` untouched per handoff.
- `sase tool run check`: fails only on same unrelated symvision stale entries.
- Targeted pytest passes: 35 passed (declaration channel/providers/plan), 58 passed (extension/journal/staged handoff).

Declaration submitted and accepted.
