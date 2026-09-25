# Chat History - ace-run (0oo.f0)

- **TIMESTAMP:** 2026-09-21 15:34:35 EDT
- **MODEL:** claude/opus
- **AGENT:** 0oo.f0

## Prompt

#gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `5`
- **Prefix reset:** historical evidence projection for older family monitor results
- **Shared ancestry reused:** `1` attributed node(s)

## Continuation Block `block:v1:7e9b96182fc78176ddc36e2306360897`

- **Node:** `legacy-boundary:20260921131544:fc374da39f43265f`
- **Kind:** `legacy_boundary`
- **Parents:** (none)
- **Content:** `compat:legacy-boundary:fc374da39f43265f`

### Opaque Legacy Boundary

This source lacks recoverable continuation node provenance, so replay does not guess transcript turns from Markdown headings.

- **Source:** family `0oo` member `0oo--plan`
- **Reason:** source lacks a recoverable continuation node
- **Transcript:** `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0oo__plan-260921_131544.md`

### Protected Legacy Content

**Protected.** This opaque snapshot is included within budget and is not reconstructed into guessed local turns.

```text
# Chat History - ace-run (0oo--plan)

- **TIMESTAMP:** 2026-09-21 13:51:58 EDT
- **MODEL:** claude/opus
- **AGENT:** 0oo--plan

## Prompt

#gh:gh_sase-org__sase Resources are spiking on this machine. I think it might be because the root
(i.e. `/`) disk is getting close to full. Can you help me confirm/deny my suspicion,
diagnose the true root cause, and fix the issue? If the issue is really low disk space,
then use `as-symlink` to clear up some space safely. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

# Gate handoff

This agent handed the remaining decision to a gate shell.
Decision: Tale ready for review: leaked_test_service_hosts.md
Gate ID: db6af8d6-89b9-4fed-896f-0c3daa1d8a20
Inspect with: sase gate show --id db6af8d6-89b9-4fed-896f-0c3daa1d8a20 --kind plan
Gate shell: 0oo--gate


```

## Continuation Block `block:v1:2a6f12a6c3d59c810cda5933b78ccf84`

- **Node:** `legacy-boundary:20260921135156:13cec7495c68c42f`
- **Kind:** `legacy_boundary`
- **Parents:** (none)
- **Content:** `compat:legacy-boundary:13cec7495c68c42f`

### Opaque Legacy Boundary

This source lacks recoverable continuation node provenance, so replay does not guess transcript turns from Markdown headings.

- **Source:** family `0oo` member `0oo--gate`
- **Reason:** source lacks a recoverable continuation node
- **Transcript:** `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0oo__gate-20260921135156.md`

### Protected Legacy Content

**Protected.** This opaque snapshot is included within budget and is not reconstructed into guessed local turns.

````text
# Chat History - ace-run (0oo--gate)

- **TIMESTAMP:** 2026-09-21 13:56:13 EDT
- **MODEL:** claude/opus
- **AGENT:** 0oo--gate

## Prompt

sase gate answer --id db6af8d6-89b9-4fed-896f-0c3daa1d8a20 --kind plan

## Response

# Tale ready for review: leaked_test_service_hosts.md

Gate state: answered
Reason: gate answered
Selected options: approve, commit

Branches:

- [x] Launch coder agent + Commit plan file to the plans sidecar (approve+commit)
- [ ] Reject (reject)
- [ ] Send Feedback (feedback)

Option results:

[
  {
    "id": "approve",
    "result": {
      "action": "approve",
      "commit_plan": true,
      "plan_archive_owner": "host",
      "plan_archive_protocol": "host_v2",
      "plan_archive_ref": "plan:202609/leaked_test_service_hosts.md",
      "plan_archive_state": "archived",
      "run_coder": true,
      "saved_plan_path": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/sase/repos/plans/202609/leaked_test_service_hosts.md"
    }
  },
  {
    "id": "commit",
    "result": {
      "action": "approve",
      "commit_plan": true,
      "run_coder": false
    }
  }
]

Output tail:

```text
$ commands/approve
{"action": "approve", "commit_plan": false, "run_coder": true}
$ commands/commit
{"action": "approve", "commit_plan": true, "run_coder": false}
```


````

## Continuation Block `block:v1:7c977d0698b61887b2c96b560aac7124`

- **Node:** `agent-delta:20260921135726:3331e3067f8bcf63`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260921135726:3331e3067f8bcf63.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-6d4eedef8d0ce0ed.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%model:@medium
#gh:gh_sase-org__sase @plan:202609/leaked_test_service_hosts.md

The above plan has been reviewed and approved. Implement it now.

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase:budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-6d4eedef8d0ce0ed.json;covered=agent-delta%3A20260921135726%3A3331e3067f8bcf63-->
# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: dygkr8va6tab
Inspect with: sase monitor show dygkr8va6tab
Monitor shell: 0oo--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29

Command:

```sh
just install && sase tool run check
```

Reason:

Verify leaked-host fix: install then just check

Next action:

Finish the approved plan 202609/leaked_test_service_hosts.md. Context: Step 1 remediation is DONE (66 leaked pytest service hosts reaped; 1 real host pid 2647210 healthy; swap 39Gi->12Gi; routines 438->10). Code fix is DONE in this workspace: platform_runner.py promotes service_lifecycle_blocked_in_tests to public; control.py start_service_host refuses the detached Popen fallback under pytest with SERVICE_LIFECYCLE_TEST_BLOCK_MESSAGE; host.py run_service_host exits 125 with the same message under pytest; tests/service/test_service_host_scenarios.py _stub_host_spawn sets SASE_SERVICE_ALLOW_LIFECYCLE_IN_TESTS=1; new tests/service/test_service_host_pytest_guard.py covers blocked start, override-allowed start, and blocked run_service_host. just fmt already ran clean; ruff on touched files passed. Your jobs: 1) Read the monitor check output (sase tool show as needed). Fix anything just check reported, then reply to the user. 2) If check is green, confirm no leak: pgrep -f [s]ase service run must be exactly 1 (pid 2647210) and no service-run environ may contain PYTEST_CURRENT_TEST (inspect /proc/PID/environ). 3) Step 4 disk: run sase disk reap preview then sase disk reap --apply (owner passes only, reaper checks liveness; never delete cargo-targets by hand; no symlinks; as-symlink does not exist). Report df -h / before/after plus reclaimable per owner. 4) Reply with before/after load, swap, process counts, disk numbers, files changed, and tests observed. Then run sase_final with a commit decision for the workspace checkout.
<!--sase:budget-span:close:1-->

## Continuation Block `block:v1:d3da9d57491aef105204efa3114f8a35`

- **Node:** `monitor-result:dygkr8va6tab:4a0c388dcdad689e`
- **Kind:** `monitor_result`
- **Parents:** `agent-delta:20260921135726:3331e3067f8bcf63`
- **Content:** `local:continuation/records/monitor_result/result:dygkr8va6tab:4a0c388dcdad689e.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_start-8dc60caf29faed86.json`
- **Intent:** `local:continuation/intents/intent:dygkr8va6tab:c71eeb2c2da10721.json`

### Monitor Result

- **Monitor ID:** `dygkr8va6tab`
- **Outcome:** `failed`
- **Exit code:** `1`
- **Cwd:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29`
- **Started:** `2026-09-21T18:13:59.501254+00:00`
- **Finished:** `2026-09-21T18:18:01.715120+00:00`
- **Elapsed:** `4m 1s`

**Command:**

```text
just install && sase tool run check
```


#### Output Evidence

- **Policy:** `auto`
- **Context:** `failed_diagnostics`
- **Retrieval:** `sase monitor show dygkr8va6tab --all-lines`
- **Evidence refs:** `file:monitor-diagnostic-manifest:dygkr8va6tab`, `file:monitor-retained-log:dygkr8va6tab`, `file:monitor-stage:lint-symvision-4130563-1790014680644783722-eca0ba39`
- **Log locators:** `diagnostics/retained_logs`

#### Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=2-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=843, output_lines=9, retained_bytes=843]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  NotificationHintFragment in src/sase/ace/tui/modals/notification_modal_constants.py
  notification_hint_fragments in src/sase/ace/tui/modals/notification_modal_constants.py
  notification_hint_tier in src/sase/ace/tui/modals/notification_modal_constants.py
error: recipe `_lint-symvision` failed on line 363 with exit code 1

```

<!--sase:budget-span:close:2-->

_Raw output omitted by the selected monitor evidence policy._

## Continuation Block `block:v1:08fb54433ab84d5e92107dfbbccc6512`

- **Node:** `agent-delta:20260921141818:e55f4f09d1e94acd`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260921141818:e55f4f09d1e94acd.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%queue(weight=1)
% xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:7c977d0698b61887b2c96b560aac7124`

- **Node:** `agent-delta:20260921135726:3331e3067f8bcf63`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260921135726:3331e3067f8bcf63.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-6d4eedef8d0ce0ed.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%model:@medium
#gh:gh_sase-org__sase @plan:202609/leaked_test_service_hosts.md

The above plan has been reviewed and approved. Implement it now.

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase: budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-6d4eedef8d0ce0ed.json;covered=agent-delta%3A20260921135726%3A3331e3067f8bcf63-->
# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: dygkr8va6tab
Inspect with: sase monitor show dygkr8va6tab
Monitor shell: 0oo--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29

Command:

```sh
just install && sase tool run check
```

Reason:

Verify leaked-host fix: install then just check

Next action:

Finish the approved plan 202609/leaked_test_service_hosts.md. Context: Step 1 remediation is DONE (66 leaked pytest service hosts reaped; 1 real host pid 2647210 healthy; swap 39Gi->12Gi; routines 438->10). Code fix is DONE in this workspace: platform_runner.py promotes service_lifecycle_blocked_in_tests to public; control.py start_service_host refuses the detached Popen fallback under pytest with SERVICE_LIFECYCLE_TEST_BLOCK_MESSAGE; host.py run_service_host exits 125 with the same message under pytest; tests/service/test_service_host_scenarios.py _stub_host_spawn sets SASE_SERVICE_ALLOW_LIFECYCLE_IN_TESTS=1; new tests/service/test_service_host_pytest_guard.py covers blocked start, override-allowed start, and blocked run_service_host. just fmt already ran clean; ruff on touched files passed. Your jobs: 1) Read the monitor check output (sase tool show as needed). Fix anything just check reported, then reply to the user. 2) If check is green, confirm no leak: pgrep -f [s]ase service run must be exactly 1 (pid 2647210) and no service-run environ may contain PYTEST_CURRENT_TEST (inspect /proc/PID/environ). 3) Step 4 disk: run sase disk reap preview then sase disk reap --apply (owner passes only, reaper checks liveness; never delete cargo-targets by hand; no symlinks; as-symlink does not exist). Report df -h / before/after plus reclaimable per owner. 4) Reply with before/after load, swap, process counts, disk numbers, files changed, and tests observed. Then run sase_final with a commit decision for the workspace checkout.
<!--sase: budget-span:close:1-->

---

% xprompts_enabled:true
# New Query
%model:muse-spark-1.3-contributor@xhigh

% xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just install && sase tool run check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-09-21T18:13:59.501254+00:00 |
| **Finished** | 2026-09-21T18:18:01.715120+00:00 |
| **Elapsed** | 4m 1s of a 1h 30m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:dygkr8va6tab`, `file:monitor-retained-log:dygkr8va6tab`, `file:monitor-stage:lint-symvision-4130563-1790014680644783722-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show dygkr8va6tab --all-lines` |

**Why this was monitored:** Verify leaked-host fix: install then just check

## Selected diagnostics

<!--sase: budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=843, output_lines=9, retained_bytes=843]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  NotificationHintFragment in src/sase/ace/tui/modals/notification_modal_constants.py
  notification_hint_fragments in src/sase/ace/tui/modals/notification_modal_constants.py
  notification_hint_tier in src/sase/ace/tui/modals/notification_modal_constants.py
error: recipe `_lint-symvision` failed on line 363 with exit code 1

```

<!--sase: budget-span:close:1-->

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-8dc60caf29faed86.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "just install && sase tool run check",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29",
    "member_agent_name": "0oo--mon",
    "monitor_id": "dygkr8va6tab",
    "next_output": "auto",
    "parent_node_ids": [],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:061c9fc64aa5777ef65899b23397c4ee26efe7cc385b0acf6fb2c24483690285",
    "starter_agent": "0oo--code",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/21/20260921135726"
  },
  "recorded_at_epoch": 1790014440.5895867,
  "schema_version": 1
}
```


## Your next action

Finish the approved plan 202609/leaked_test_service_hosts.md. Context: Step 1 remediation is DONE (66 leaked pytest service hosts reaped; 1 real host pid 2647210 healthy; swap 39Gi->12Gi; routines 438->10). Code fix is DONE in this workspace: platform_runner.py promotes service_lifecycle_blocked_in_tests to public; control.py start_service_host refuses the detached Popen fallback under pytest with SERVICE_LIFECYCLE_TEST_BLOCK_MESSAGE; host.py run_service_host exits 125 with the same message under pytest; tests/service/test_service_host_scenarios.py _stub_host_spawn sets SASE_SERVICE_ALLOW_LIFECYCLE_IN_TESTS=1; new tests/service/test_service_host_pytest_guard.py covers blocked start, override-allowed start, and blocked run_service_host. just fmt already ran clean; ruff on touched files passed. Your jobs: 1) Read the monitor check output (sase tool show as needed). Fix anything just check reported, then reply to the user. 2) If check is green, confirm no leak: pgrep -f [s]ase service run must be exactly 1 (pid 2647210) and no service-run environ may contain PYTEST_CURRENT_TEST (inspect /proc/PID/environ). 3) Step 4 disk: run sase disk reap preview then sase disk reap --apply (owner passes only, reaper checks liveness; never delete cargo-targets by hand; no symlinks; as-symlink does not exist). Report df -h / before/after plus reclaimable per owner. 4) Reply with before/after load, swap, process counts, disk numbers, files changed, and tests observed. Then run sase_final with a commit decision for the workspace checkout.
% xprompts_enabled:true

### Assistant

Plan `202609/leaked_test_service_hosts.md` is complete. Final declaration accepted (commit).

## Leak check: clean

- `sase service run` processes: exactly 1, before and after. PID changed 2647210 → 185759 (service manager restarted the real host mid-turn); environ has zero `PYTEST_CURRENT_TEST` markers.
- Significant: several sibling pytest suites ran concurrently during this turn and spawned zero extra hosts — the guard holds fleet-wide.

## Before / after

| | Before | After |
|---|---|---|
| Load (1/5/15) | 13.47 / 19.50 / 31.56 | 18.32 / 20.77 / 22.55 |
| Swap used (of 63 GiB) | 14 GiB | 16 GiB |
| Service-run procs | 1 (clean) | 1 (clean) |
| Disk `/` | 830G used, 37G avail, 96% | 724G used, 142G avail, 84% |

Disk reap preview reported ~114.6 GiB reclaimable (managed_tmp_reaper 111.95, workspace_compact 2.65, artifact_run_retention 0.04). Apply reclaimed ~119 GiB via owners; `artifact_run_retention` (~45 MiB) refused with `authoritative_protection_unavailable` — reported as-is, not retried. Never touched cargo-targets by hand; no symlinks involved.

## `just check`: lint green, test lane has pre-existing failures

The monitor's symvision failure reproduced on the clean tree (leftover from commit `03fff9dcb`). Fixed per the symvision hierarchy by privatizing the three in-file/test-only helpers (`_NotificationHintFragment`, `_notification_hint_fragments`, `_notification_hint_tier`) in [notification_modal_constants.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/ace/tui/modals/notification_modal_constants.py) plus its test import. All lint gates now pass.

Full lane (escalated to 44552 tests): 44552 passed, 15 failed. Triage against the stashed clean tree:

- 4 pass serially — xdist load flakes (3 usage-config params, 1 epic-arrival frame).
- 11 fail identically with and without my changes — pre-existing HEAD drift (bead free-text options, usage-config provider map, completion snapshot, shard timing table at 20.8% vs 20% limit, commit-bead `env=None`, session reporter, import budget, question footer). Left untouched as unrelated; they need owner triage, possibly task beads.

## Files changed / tests observed

- [platform_runner.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/service/platform_runner.py), [control.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/service/control.py), [host.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/service/host.py): pytest guard (from prior work, verified here).
- [test_service_host_pytest_guard.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/tests/service/test_service_host_pytest_guard.py) (new), [test_service_host_scenarios.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/tests/service/test_service_host_scenarios.py): override opt-in.
- Targeted run: 21/21 pass (hint footer, guard, scenarios).

---

%xprompts_enabled:true
# New Query

 Are there any processes running on my apollo machine related to this? Should they be killed?

## Response

Apollo has the same leak: 12 orphaned pytest service hosts. I'm checking whether apollo's installed sase already has the fix and how much disk the pytest temp directories use.

Yes. Apollo has the same leak as athena, and I recommend killing the leaked processes. I only looked; I haven't killed anything on apollo.

## What's running on apollo

- **12 leaked `sase service run` hosts.** Each one has `PYTEST_CURRENT_TEST` set and a `HOME` under `/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-{8,12,13}/…`. They were started by the same four ace TUI tests (`test_agents_pane_mount`, `test_artifacts_agents_loading`, `test_residual_freeze_soak`, `test_startup_stopwatch_live_update`) during three separate pytest runs. They are 2h16m to 18h38m old and now belong to init (ppid 1).
- **Each leaked host runs its own `sase scheduler run`** plus a full set of routines (hooks, waits, housekeeping, …). That's why apollo has **79** `sase axe routine run` processes. The hooks routines keep starting `sase_job_*` cleanup and sync jobs against the fake pytest homes, each using about 85–90% CPU while it runs. The service hosts alone hold about 880 MB of memory.
- **The real host is healthy:** PID 3960349, started by `systemd --user`, with no pytest markers. The gateway and the 7 real routines hang off it. Leave these alone.

Machine state right now: load is **25.5 / 22.8 / 20.6** on a 31 GiB box with no swap, and **`/` is 98% full (5.8 GB free)**.

## Should they be killed?

Yes. They do no real work, they burn CPU, and they won't exit on their own. Apollo's sase is an editable install of `~/projects/github/sase-org/sase`, which already contains the fix (`562d52db0`, guard confirmed). New test runs there shouldn't leak, but these 12 processes started before the fix.

To kill each leaked host along with its scheduler and routines:

```sh
ssh apollo 'real=3960349
for h in $(pgrep -f "[s]ase service run"); do
  [ "$h" = "$real" ] && continue
  tr "\0" "\n" </proc/$h/environ | grep -q ^PYTEST_CURRENT_TEST= || continue
  s=$(pgrep -P $h | paste -sd,); r=${s:+$(pgrep -P $s | paste -sd,)}
  kill -TERM $h ${s//,/ } ${r//,/ } 2>/dev/null
done
sleep 5; pgrep -af "[s]ase service run"; pgrep -fc "[s]ase axe routine run"'
```

It skips the real host and anything without the pytest marker. Afterwards you should see exactly 1 service host and about 7 routines. Any `sase_job_*` processes still running will finish their current cycle and exit.

## Other things I noticed on apollo

- **The disk is the bigger long-term risk.** The leaked hosts' temp directories are small (2.2 GB total in `/var/tmp`). The big users are `~/.cache` (73G), `~/.local/state/sase/workspaces` (37G) and the `sase-core/target` build directory (24G). After killing the leaked hosts, run `sase disk reap` (preview, then `--apply`) on apollo, as we did on athena.
- **Other load in the snapshot:** a `sase-core` rebuild (`dev-update`) was compiling, and a `sase tui --restart-service` had been running for 2h25m. Both are separate from the leak and probably expected. A visual pytest run (`-n 5`) and a mypy run in `sase_16` were also active, but those were short-lived at the time I looked.

If you'd like, I can run the kill and the disk reap on apollo next turn.
