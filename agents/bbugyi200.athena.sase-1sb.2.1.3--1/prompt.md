%queue(weight=1)
#fork:sase-1sb.2.1.3--plan
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
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-11-12T08:01:41.181734+00:00 |
| **Finished** | 2026-11-12T08:46:01.674321Z |
| **Elapsed** | 19m 13s of a 1h 0m 0s budget |
| **Output** | 4 KiB · evidence refs: `file:monitor-diagnostic-manifest:q277j9348xd0`, `file:monitor-retained-log:q277j9348xd0` · raw output omitted: `facts_only` · full log: `sase monitor show q277j9348xd0 --all-lines` |
| **Tool run** | sase tool show 31f44f89bd7e0d0da8f3467cce5c73c7 |

**Why this was monitored:** Verify hook enforcement before host completion

## Failure triage

verdict: pass

KNOWN 0; FLAKY 0

sase tool show 31f44f89bd7e0d0da8f3467cce5c73c7 -j

## Host completion

Verification COMPLETED — exit 0, but host completion did not land the change.

- `stale_worktree_fingerprint` — the worktree changed after the completion was sealed — re-prepare the completion on the current tree.

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%macros_enabled:true