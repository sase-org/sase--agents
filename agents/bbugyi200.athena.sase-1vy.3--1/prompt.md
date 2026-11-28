%queue(weight=1)
#fork:sase-1vy.3--code
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
sase tool run check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-11-28T10:59:51.028242+00:00 |
| **Finished** | 2026-11-28T11:34:19.347317Z |
| **Elapsed** | 0.672s of a 1h 0m 0s budget |
| **Output** | 40 KiB · evidence refs: `file:monitor-diagnostic-manifest:g198whks0eaf`, `file:monitor-retained-log:g198whks0eaf` · raw output omitted: `facts_only` · full log: `sase monitor show g198whks0eaf --all-lines` |
| **Tool run** | sase tool show 568ad1c5476e635c221478004600d06e |

**Why this was monitored:** finish axe sample-window check (joined run)

## Failure triage

verdict: pass

KNOWN 0; FLAKY 0

sase tool show 568ad1c5476e635c221478004600d06e -j

## Your next action

Check run 568ad1c5476e635c221478004600d06e holds `sase tool run check` for the axe sample-window fix. Read it with `sase tool show 568ad1c5476e635c221478004600d06e`. Focused regressions already green (test_bench_tui_jk_sample_window.py + test_services_tab_id.py, 12 passed), slow benchmark isolation verified (20 next +20 prev, tab==services, window-complete passes) with p95 over-budget on both fixed and clean base (see sase-1vy.3 follow-up note), guard red-on-old/green-on-new demonstrated. Investigate any NEW/UNKNOWN check failures with clean-base evidence, retain the true result, run `sase bead epic-symbols sase-1vy.3` immediately before closing, then close only sase-1vy.3 with a note naming the fix, regression evidence, focused benchmark outcome, check run ID, and clean-base p95 evidence. Leave sase-199 and ancestors to the land agent. Finish through /sase_final with a commit decision for the primary repo.
%macros_enabled:true