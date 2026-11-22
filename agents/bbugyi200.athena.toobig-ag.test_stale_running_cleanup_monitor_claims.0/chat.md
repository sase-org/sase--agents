# Chat History - ace-run (toobig-ag.test_stale_running_cleanup_monitor_claims.0)

- **TIMESTAMP:** 2026-11-21 23:56:10 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** toobig-ag.test_stale_running_cleanup_monitor_claims.0

## Prompt

%id(test_stale_running_cleanup_monitor_claims.0, clan=toobig-ag)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_stale_running_cleanup_monitor_claims.py` file into multiple files? Use your best
%wait:toobig-ag.gc_policy_policy.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I’ll inspect the test file and repository guidance first, then split it along the existing test/helper boundaries and verify the three requested linters individually before running `sase tool run check`.

The file is 757 lines and has several distinct clusters: stale claim cleanup cases, monitor import isolation, and leaked monitor retention repair. I’m reading the required lint guidance and mapping the definitions/imports/monkeypatch points before moving code, so the facade preserves callers and patch targets.

The split is in place: the original module is now a 34-line collection/import facade, with focused terminal-claim, monitor-import, and retention modules at 227, 114, and 432 lines. All three test functions groups are exposed through the original path, and the private helpers stay local to their support modules. I’m starting the requested lint gates one at a time.

All three requested gates passed individually: Symvision, mypy, and toobig. The final `sase tool run check` can take several minutes here, so I’m following the repository’s monitor workflow; first I’m reviewing that workflow and formatting the checkout before staging the check.

The requested `sase tool run check` is still running after its formatting, Ruff, mypy, and feature-flag stages; it has not reported an escalation or failure. I’m waiting on this same run and will use its result as the final check evidence.

The full check stopped at the repository-wide docs contract because `docs/reference/automation/notification-gates.md` exceeds its 6,000-word cap; the check did not reach tests. I ran the split module directly in the project virtualenv, and all 13 tests pass. I’m doing a final diff/line-count check now; the reported docs issue is outside the files changed for this split.

Split the tests into three focused modules while keeping the original module as the collection and import facade. All four files are under 500 lines; the largest is 432.

- **Verification:** `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` passed individually. The split module’s 13 tests passed.
- **Full check:** `sase tool run check` stopped at the docs contract: `notification-gates.md` exceeds its 6,000-word cap. That file is outside this change.
- The finalizer declaration was accepted.

Files: [facade](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_stale_running_cleanup_monitor_claims.py>), [terminal cases](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/_stale_running_cleanup_monitor_claims_terminal.py>), [import cases](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/_stale_running_cleanup_monitor_claims_imports.py>), [retention cases](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/_stale_running_cleanup_monitor_claims_retention.py>).
