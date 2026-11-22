# Chat History - ace-run (toobig-ai.test_machine_capacity_report_feed.0)

- **TIMESTAMP:** 2026-11-22 12:01:43 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-ai.test_machine_capacity_report_feed.0

## Prompt

%auto
%id(test_machine_capacity_report_feed.0, clan=toobig-ai)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_machine_capacity_report_feed.py` file into multiple files? Use your best
%wait:toobig-ai.auto_refresh.0
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

Split done. The 751-line `tests/ace/tui/test_machine_capacity_report_feed.py` is now 5 files, each well under 500 lines, following the repo's `test_launchable_mru.py` facade precedent:

- [test_machine_capacity_report_feed.py](/absolute/path/to/tests/ace/tui/test_machine_capacity_report_feed.py) (53 lines) — facade re-exporting all 18 public `test_*` names; original import path preserved, no `_private` re-exports.
- [_machine_capacity_report_feed_helpers.py](/absolute/path/to/tests/ace/tui/_machine_capacity_report_feed_helpers.py) (136 lines) — shared fixtures with public names only: `make_report`, `make_agent`, `FeedApp`.
- [_machine_capacity_report_feed_authoritative_tests.py](/absolute/path/to/tests/ace/tui/_machine_capacity_report_feed_authoritative_tests.py) (160 lines) — 3 authoritative-report tests.
- [_machine_capacity_report_feed_lifecycle_tests.py](/absolute/path/to/tests/ace/tui/_machine_capacity_report_feed_lifecycle_tests.py) (186 lines) — 7 feed-lifecycle tests.
- [_machine_capacity_report_feed_revalidation_tests.py](/absolute/path/to/tests/ace/tui/_machine_capacity_report_feed_revalidation_tests.py) (308 lines) — 8 revalidation tests plus single-use helpers (`_FakeClock`, `_stable_feed`, `_run_tick`, `_installed_count`, `_ExpiringOverride`) kept local to that file.

No new module imports a `_`-prefixed name from another new module, and the private `_*_tests.py` filenames avoid double pytest collection. `make_agent` duplicates the `_agent` construction locally so no private cross-file import was needed.

Verification observed:
- `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig` each exit 0 (the one toobig warning is a pre-existing unrelated file).
- Facade run: 18 passed.
- `sase tool run check` (run `4e0da9ade879ed09ada6477d276af010`): all lint stages pass; scoped lane ran 1169 passed with 3 failures, and I proved all 3 pre-existing by re-running them with my changes stashed — they fail identically on the untouched base and audit files this split never touched (`src/sase/axe/*`, `docs/`). The scoped lane itself shows all 18 split tests passing.

Declaration accepted for `commit`. Split work preserved for host commit.
