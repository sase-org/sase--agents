# Chat History - ace-run (1de--code)

- **TIMESTAMP:** 2026-11-17 10:32:22 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 1de--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202611/install_scoped_update_status_snapshot.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved plan ([install_scoped_update_status_snapshot.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/sase/repos/plans/202611/install_scoped_update_status_snapshot.md)).

**What changed**
- [cache.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/updates/cache.py): snapshot is now keyed by install — `current_install_prefix()` (resolved `sys.prefix`) hashed to 12 hex chars in the filename, `install_prefix` recorded in the envelope, reads with a missing/foreign prefix treated as cache misses, `SCHEMA_VERSION` bumped to 5, and default-path writes prune the legacy unkeyed file plus stale (>7d) sibling keyed files, best-effort and never raising. Callers needed no signature changes.
- [update_run.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/ace/tui/actions/update_run.py): after a no-op comprehensive-update preview, ACE now schedules updates-indicator revalidation (drop-only, worker thread) so the badge can't disagree with the preview toast.
- [__init__.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/src/sase/updates/__init__.py): exports `current_install_prefix`.
- Tests: [test_update_status_snapshot.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_update_status_snapshot.py) gained prefix-scoping, missing/foreign-prefix miss, and legacy/stale-pruning tests (schema assertion updated to 5); [test_update_run_actions.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/ace/tui/test_update_run_actions.py) now asserts the revalidation hook fires on no-op previews and not on runnable/error paths.

**Verification**
- Targeted: 49 passed across the snapshot, cache-orchestration, update-run, and plugins-loading-freshness suites.
- `sase tool run check` (run `ad73244da507174b23c14013238a7d1b`): all lint gates, SASE validation, committed plans, and the diff-scoped test lane passed, exit 0.

Final declaration accepted; the host will commit the `main` checkout after this turn.
