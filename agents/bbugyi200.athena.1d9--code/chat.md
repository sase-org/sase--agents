# Chat History - ace-run (1d9--code)

- **TIMESTAMP:** 2026-11-17 07:17:59 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 1d9--code

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: c9x8xm3qxdm8
Inspect with: sase monitor show c9x8xm3qxdm8
Monitor turn: 1d9--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

The joined `sase tool run check` covers the unmanaged_project_axe_noise implementation (sdd_store_not_applicable predicate, retention skips, publication-job skip handling, docs, and new tests in tests/sdd_store/test_store_not_applicable.py, tests/core/test_agent_artifact_run_protection_unconnected.py, tests/test_artifact_protection_scan.py, tests/agents_sync/_publication_job_targets.py). If the run is green, submit /sase_final with a commit decision for the sase repo. If it is red, fix the failures (new tests and targeted suites already passed inline: test_store_not_applicable, test_auto_init, test_agent_artifact_run_protection_unconnected, test_artifact_protection_scan, test_publication_job, plus related retention/CLI suites), then rerun verification before declaring.


## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202611/unmanaged_project_axe_noise.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved `202611/unmanaged_project_axe_noise.md` plan. All source, docs, and test changes are in the tree; full `just check` verification is still running under a staged monitor.

What changed:

- New `sdd_store_not_applicable()` predicate in [store.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/sdd/store.py), true only for unconnected primaries with a cleanly unmanaged `sase.yml`. Invalid YAML, non-bool markers, layout collisions, and unreadable store records all fail closed. `auto_connect_sdd_store` keeps its exact behavior with a comment tying its check to the predicate.
- Both retention scanners skip required beads/plans sources for not-applicable projects (computed at most once per project) via a new `sidecar_protection_not_applicable()` helper in [_sidecar_protection_label.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/core/_sidecar_protection_label.py). Live sidecar roots are still always scanned.
- `agent_publication` no longer errors or rings the doorbell for missing targets: skips with no queued rows are silent (`target_skipped`), skips with queued rows count one error naming the skip reason and stay visible in `active_remaining`, and selection-time errors are counted once. Other ring sites are unchanged, and no heartbeat schema change was needed (`last_outcome` is free-form; only `publisher_is_live` reads the heartbeat).
- Docs updated in [sdd-storage.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/docs/contribute/sdd-storage.md), [scheduler-default-routines.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/docs/reference/automation/scheduler-default-routines.md), and [scheduler-housekeeping.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/docs/reference/automation/scheduler-default-routines.md) (the actual `agent_publication` reference). `default_config.yml` left untouched since the routine docs are hand-written, not generated from it. No `sase-core` change.
- Tests: new [test_store_not_applicable.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/sdd_store/test_store_not_applicable.py) (7 cases), unmanaged/managed/live matrix plus an end-to-end plan test in the run-retention and file-retention suites (existing unconnected fixtures marked managed to preserve fail-closed coverage), and new [_publication_job_targets.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/agents_sync/_publication_job_targets.py) (skip-silent, skip-with-rows, error-counted-once, sibling-drains) wired into `test_publication_job.py`.

Verification so far: all targeted suites pass (sdd_store 266, publication_job 23, retention/CLI/prune suites), and `sase tool run check` cleared every lint gate including mypy and symvision before escalating on the long test lane (run `424a65e88ceaf9277642655147fa8e6b`). That run is joined to staged monitor `c9x8xm`; its follow-up will finish verification and submit the commit declaration.
