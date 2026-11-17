%queue(weight=1)
#fork:sase-1t2.11.1.5--plan
%model:muse-spark-1.3-contributor@xhigh

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
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-11-17T02:50:38.884277+00:00 |
| **Finished** | 2026-11-17T02:53:18.111403Z |
| **Elapsed** | 3s of a 1h 0m 0s budget |
| **Output** | 7 KiB · evidence refs: `file:monitor-diagnostic-manifest:bzkqhzsjzq81`, `file:monitor-retained-log:bzkqhzsjzq81` · raw output omitted: `facts_only` · full log: `sase monitor show bzkqhzsjzq81 --all-lines` |
| **Tool run** | sase tool show e1593b99e3aae797b82c5051c2cf8953 |

**Why this was monitored:** finish check (joined run)

## Failure triage

verdict: pass

KNOWN 0; FLAKY 0

sase tool show e1593b99e3aae797b82c5051c2cf8953 -j

## Your next action

On completion run sase tool show e1593b99e3aae797b82c5051c2cf8953, close bead sase-1t2.11.1.5 with the verification note if green, else report the failure
%macros_enabled:true