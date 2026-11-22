%queue(weight=1)
#fork:1f5--code
%model:grok-4.6@medium

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-22T14:08:08.493317+00:00 |
| **Finished** | 2026-11-22T14:13:47.124034Z |
| **Elapsed** | 4m 16s of a 45m 0s budget |
| **Output** | 2 KiB · evidence refs: `file:monitor-diagnostic-manifest:da2etf32fymn`, `file:monitor-retained-log:da2etf32fymn`, `file:monitor-stage:lint-docs-contract-4131812-1795356823847826610-45f013c8` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show da2etf32fymn --all-lines` |
| **Tool run** | sase tool show 3eeb0585324dfdba27482f42f17480bf |

**Why this was monitored:** Verify lazy running_field import-cycle fix before host completion

## Failure triage

verdict: undetermined — 1 UNKNOWN; exit 1

UNKNOWN lint (docs contract): error: recipe `docs-lint` failed on line 1080 with exit code 1 — extractor_generic; no owner
KNOWN 0; FLAKY 0

sase tool show 3eeb0585324dfdba27482f42f17480bf -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (docs contract) (failed exit 1) ==
[counts: output_bytes=822, output_lines=7, retained_bytes=822]
.venv-format/bin/python tools/check_docs
warning: contribute/development.md: over budget at 12611 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
warning: contribute/perf-runbook.md: over budget at 15086 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
warning: contribute/rust-backend.md: over budget at 10988 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
error: reference/automation/notification-gates.md: over budget at 6158 words (cap 6000 for reference/). This page may not grow. Split it: anything longer than one goal is two guides.
check_docs: 1 error(s)
error: recipe `docs-lint` failed on line 1080 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true