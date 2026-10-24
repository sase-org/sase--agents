%queue(weight=1)
#fork:13t--1
%model:muse-spark-1.3-contributor
%effort:xhigh

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
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-10-24T19:42:31.386007+00:00 |
| **Finished** | 2026-10-24T20:15:28.878201Z |
| **Elapsed** | 32m 56s of a 1h 0m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:8zqjbqzbwb2e`, `file:monitor-retained-log:8zqjbqzbwb2e` · raw output omitted: `facts_only` · full log: `sase monitor show 8zqjbqzbwb2e --all-lines` |
| **Tool run** | sase tool show a628c85b5f58556edc4d504642e55df2 |

**Why this was monitored:** run command

## Failure triage

verdict: pass

KNOWN 0; FLAKY 0

sase tool show a628c85b5f58556edc4d504642e55df2 -j

## Host completion

Verification COMPLETED — exit 0, but host completion did not land the change.

- `outstanding_finalizer_actions`

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%macros_enabled:true