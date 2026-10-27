%queue(weight=1)
#fork:toobig-8j.failed_close_recovery.0--plan
%model:grok-4.6
%effort:high

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
| **Started** | 2026-10-27T03:26:02.420217+00:00 |
| **Finished** | 2026-10-27T03:39:24.799062Z |
| **Elapsed** | 13m 21s of a 1h 0m 0s budget |
| **Output** | 5 KiB · evidence refs: `file:monitor-diagnostic-manifest:tgdcxtggsaz4`, `file:monitor-retained-log:tgdcxtggsaz4` · raw output omitted: `facts_only` · full log: `sase monitor show tgdcxtggsaz4 --all-lines` |
| **Tool run** | sase tool show 7518bfe72d1247ef35036cff77f211bd |

**Why this was monitored:** Verify failed_close_recovery split before host completion

## Failure triage

verdict: pass

KNOWN 0; FLAKY 0

sase tool show 7518bfe72d1247ef35036cff77f211bd -j

## Host completion

Verification COMPLETED — exit 0, but host completion did not land the change.

- `outstanding_finalizer_actions`

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%macros_enabled:true