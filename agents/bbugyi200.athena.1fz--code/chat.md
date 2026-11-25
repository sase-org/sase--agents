# Chat History - ace-run (1fz--code)

- **TIMESTAMP:** 2026-11-25 10:32:06 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 1fz--code

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: h6w3nnmxqve0
Inspect with: sase monitor show h6w3nnmxqve0
Monitor turn: 1fz--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

Inspect the joined check run result with sase tool show; fix any NEW failures in the stranded toast/degraded-report change, then finish through /sase_final.


## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202611/stranded_toast_flood.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- coalesce = coalesce (planner default: coalesce). Implement the "coalesce = coalesce" branch; ignore "coalesce = per_leaf". Context: "Should one warmup pass that finds more than three newly stranded beads collapse into a single summary toast?".
Implement only the branches selected above.
%macros_enabled:true


## Response

Implemented the approved `stranded_toast_flood` plan (coalesce branch) in the `sase` checkout.

Changed:
- [stranded_work_facade.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/core/stranded_work_facade.py): added `STRANDED_UNKNOWN_RECORDS_UNAVAILABLE = "records_unavailable"` mirroring sase-core.
- [stranded.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/bead/stranded.py): added `StrandedReport.records_unavailable` + `degraded` property; `load_stranded_report()` counts `unknown`/`records_unavailable` verdicts.
- [agent_stranded.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/models/agent_stranded.py): `warm_stranded_work_reports()` skips a degraded snapshot when the previous entry is complete, with `stranded_degraded_skips` telemetry; cold/degraded-over-degraded still installs.
- [_stranded_toasts.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_stranded_toasts.py): rewrote to incident-keyed toasts (`last_turn_artifact_dir or last_turn or session or bead_id`), `_SEEN_LEAVES: dict[str, dict[str, str]]`, no removal on flap, degraded reports skipped, deterministic ordering, coalesce summary `⚐ {n} beads newly stranded: {id1}, {id2}, {id3} (+{n-3} more).` for >3.
- [bead-lifecycles.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/docs/reference/work-units/bead-lifecycles.md): added incident-once + summary-burst + keep-last-complete-report sentences.

Tests:
- New [test_stranded_degraded_refresh.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_stranded_degraded_refresh.py): 4 passed (lock-busy degraded, degraded skip + reinstall, cold install, degraded-over-degraded).
- New [test_stranded_toasts.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_stranded_toasts.py): 6 passed plus existing `test_stranded_transition_toast_uses_quiet_first_baseline` (7 total).
- `test_stranded_stable_refresh` + batch + facade suites: 25 passed.

Full `just check` via `sase tool run check` (run `465ab20b9d95b85fcf6c574936b0cd90`) was still running after 8m30s; handed to staged verify monitor `h6w3nn` with carry of the dirty tree. The follow-up will inspect that run, fix any new failures, and finish.
