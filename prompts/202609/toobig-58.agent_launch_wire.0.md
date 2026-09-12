- **AGENTS:**
  - [bbugyi200.athena.toobig-58.agent_launch_wire.0--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.toobig-58.agent_launch_wire.0.md)

#fork:toobig-58.agent_launch_wire.0--plan %model:grok-4.6 %effort:xhigh

%xprompts_enabled:false

# Monitored command finished

**Command:**

```text
just test
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23
```

|              |                                                                                                                                                                                                                                                                                            |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Outcome**  | FAILED — exit 1                                                                                                                                                                                                                                                                            |
| **Started**  | 2026-09-11T23:46:57.067443+00:00                                                                                                                                                                                                                                                           |
| **Finished** | 2026-09-12T00:07:41.837396+00:00                                                                                                                                                                                                                                                           |
| **Elapsed**  | 20m 43s of a 45m 0s budget                                                                                                                                                                                                                                                                 |
| **Output**   | 246 KiB · evidence refs: `file:monitor-diagnostic-manifest:jkrwk7azsn2g`, `file:monitor-retained-log:jkrwk7azsn2g`, `file:monitor-stage:stage-one-849328-1789170999408058525-6d615955` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show jkrwk7azsn2g --all-lines` |

**Why this was monitored:** Verify the agent_launch_wire split; scoped selection
escalated to the full suite

## Your next action

Continue the agent_launch_wire.py split. The public import path is still
sase.core.agent_launch_wire. Implementations live in agent_launch_wire_records.py
(dataclasses), agent_launch_wire_conversion.py (to_json), and
agent_launch_wire_from_dict.py (from_dict hydrators). _LaunchPlanDiagnosticWire was
renamed to public LaunchPlanDiagnosticWire so conversion can import it without a private
cross-file symbol.

Already verified before this monitor: ruff format/check, mypy (whole src), toobig, and
tests/core/test*agent_launch_wire_contract.py plus fanout/preview wire tests. just check
/ just check-full cannot pass on this tree because HEAD already fails just
_lint-symvision on unrelated private cross-file imports in
src/sase/main/update_handler*\*.py (and similar); do not expand scope to fix those.

If just test failed, fix only split-related failures, re-run the failing tests, then
reply. If it passed, reply to the user summarizing the split (file layout, line counts,
unchanged import path) and that verification ran. Either way, end with /sase_final and
commit the split. %xprompts_enabled:true
