# Chat History - ace-run (sase-17r)

- **TIMESTAMP:** 2026-09-24 09:55:17 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17r

## Prompt

#gh:gh_sase-org__sase
%id(sase-17r, bead=sase-17r)
%m:@medium
Can you complete the work for task bead sase-17r by running the `sase bead read sase-17r -r "Need the task scope"` command,
reviewing the command's output, doing the work, and then closing the bead by running the
`sase bead close sase-17r --note "<what you verified>"` command?

If you discover genuinely distinct follow-up work that is outside this task, use `/sase_new_task` with details
identifying the current bead; it will corroborate a duplicate, attach a causally related active-epic issue, or
create a sized task as appropriate.

## Response

Done — task bead sase-17r is complete and closed.

**Fix:** `maybe_gc_sidecar_clone` only fired on loose-object *count* (>2,000), so the reported 1,891-object / 1.15 GiB reference clone never got packed and every fresh-workspace `--dissociate` clone repacked ~1.2 GiB (~22s p50). It now also fires when loose-object *bytes* exceed 256 MiB, via a single-walk `_loose_object_stats()` helper. The existing scheduler path (`sidecar_auto_sync` chop) picks this up with no other changes.

**Changed files:**
- [src/sase/sdd/_store_maintenance.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/sdd/_store_maintenance.py) — bytes threshold + stats helper
- [tests/sdd_store/test_store_maintenance.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/tests/sdd_store/test_store_maintenance.py) — 3 regression tests

**Verification observed:** 9/9 tests pass under the repo harness; the 3 new tests fail on pre-change code and pass after; ruff check/format clean; mypy gate passed; bytes trigger confirmed against the real 2,492-object / 1.62 GiB beads clone. Final declaration accepted (host commits).

**Two pre-existing issues, both confirmed identical on the base tree and not caused by this change:** `just check` stops at the `_lint-symvision` backlog (73 unused symbols, none in touched files — already noted on existing beads, so no duplicate filed), and this workspace's editable `sase_core_rs` initially lacked its compiled extension (the check run's setup built it, which repaired the test env).
