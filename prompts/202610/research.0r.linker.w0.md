- **AGENTS:**
  - [bbugyi200.apollo.research.0r.linker.w0--2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0r.linker.w0.md)

%queue(weight=1) #fork:research.0r.linker.w0--1 %model:muse-spark-1.3-contributor@xhigh

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

|              |                                                                                                                                                                                                                                                                                                |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Outcome**  | FAILED — exit 1                                                                                                                                                                                                                                                                                |
| **Started**  | 2026-10-09T23:58:36.455054+00:00                                                                                                                                                                                                                                                               |
| **Finished** | 2026-10-10T00:06:03.593834+00:00                                                                                                                                                                                                                                                               |
| **Elapsed**  | 7m 26s of a 1h 0m 0s budget                                                                                                                                                                                                                                                                    |
| **Output**   | 5 KiB · evidence refs: `file:monitor-diagnostic-manifest:mesgaabp1agx`, `file:monitor-retained-log:mesgaabp1agx`, `file:monitor-stage:lint-symvision-2237451-1791590760241758618-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show mesgaabp1agx --all-lines` |
| **Tool run** | sase tool show e402281007a4c422d8c0431a23cc56e6                                                                                                                                                                                                                                                |

**Why this was monitored:** Verify before host completion

## Failure triage

verdict: new_failures — 12 NEW; exit 1

NEW lint (symvision): auto_restart_recovery_is_in_flight in
src/sase/core/agent_auto_restart_facade.py — recorded evidence; no owner NEW lint
(symvision): AgentFailureFrameWire in src/sase/core/agent_auto_restart_wire.py —
recorded evidence; no owner NEW lint (symvision): claim_auto_restart_ledger in
src/sase/core/agent_auto_restart_facade.py — recorded evidence; no owner NEW lint
(symvision): AgentFailureAttributeErrorWire in src/sase/core/agent_auto_restart_wire.py
— recorded evidence; no owner NEW lint (symvision): AutoRestartProbeWire in
src/sase/core/agent_auto_restart_wire.py — recorded evidence; no owner NEW lint
(symvision): AgentFailureChainLinkWire in src/sase/core/agent_auto_restart_wire.py —
recorded evidence; no owner NEW lint (symvision): AgentFailureImportErrorWire in
src/sase/core/agent_auto_restart_wire.py — recorded evidence; no owner NEW lint
(symvision): advance_auto_restart_ledger in src/sase/core/agent_auto_restart_facade.py —
recorded evidence; no owner NEW lint (symvision): python_wire_schema_version in
src/sase/core/agent_auto_restart_facade.py — recorded evidence; no owner NEW lint
(symvision): AutoRestartLedgerHistoryWire in src/sase/core/agent_auto_restart_wire.py —
recorded evidence; no owner KNOWN 0; FLAKY 0

sase tool show e402281007a4c422d8c0431a23cc56e6 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->

**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=2310, output_lines=20, retained_bytes=2310]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.37.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  AgentFailureAttributeErrorWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureChainLinkWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureFrameWire in src/sase/core/agent_auto_restart_wire.py
  AgentFailureImportErrorWire in src/sase/core/agent_auto_restart_wire.py
  AutoRestartLedgerHistoryWire in src/sase/core/agent_auto_restart_wire.py
  AutoRestartProbeWire in src/sase/core/agent_auto_restart_wire.py
  advance_auto_restart_ledger in src/sase/core/agent_auto_restart_facade.py
  auto_restart_lineage_root in src/sase/core/agent_auto_restart_facade.py
  auto_restart_recovery_is_in_flight in src/sase/core/agent_auto_restart_facade.py
  claim_auto_restart_ledger in src/sase/core/agent_auto_restart_facade.py
  derive_auto_restart_episode in src/sase/core/agent_auto_restart_facade.py
  python_wire_schema_version in src/sase/core/agent_auto_restart_facade.py
error: Recipe `_lint-symvision` failed on line 440 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the
original task. %macros_enabled:true
