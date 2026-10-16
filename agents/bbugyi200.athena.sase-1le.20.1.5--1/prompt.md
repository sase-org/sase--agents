%queue(weight=1)
#fork:sase-1le.20.1.5--plan
%model:grok-4.6@high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-16T17:17:10.959332+00:00 |
| **Finished** | 2026-10-16T17:19:48.119892Z |
| **Elapsed** | 2m 36s of a 1h 0m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:8g9g3fe2zv7e`, `file:monitor-retained-log:8g9g3fe2zv7e`, `file:monitor-stage:lint-pyscripts-3902170-1792171184894688950-75497c76` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 8g9g3fe2zv7e --all-lines` |
| **Tool run** | sase tool show 3e8d091731ee3be5ece32a181607ff85 |

**Why this was monitored:** Verify tui-prompt-move (sase-1le.20.1.5)

## Failure triage

verdict: undetermined — 1 UNKNOWN; exit 1

UNKNOWN lint (pyscripts): error: recipe `_lint-pyscripts` failed on line 377 with exit code 1 — extractor_generic; no owner
KNOWN 0; FLAKY 0

sase tool show 3e8d091731ee3be5ece32a181607ff85 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (pyscripts) (failed exit 1) ==
[counts: output_bytes=1219, output_lines=8, retained_bytes=1219]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.40.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
.venv/bin/python tools/pyscripts-260801
[Rule 1] Unused: site/reference/automation/tools/index.html is not referenced in site/reference/automation/
error: recipe `_lint-pyscripts` failed on line 377 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true