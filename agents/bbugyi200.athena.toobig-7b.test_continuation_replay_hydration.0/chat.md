# Chat History - ace-run (toobig-7b.test_continuation_replay_hydration.0)

- **TIMESTAMP:** 2026-10-07 19:13:01 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-7b.test_continuation_replay_hydration.0

## Prompt

%id(test_continuation_replay_hydration.0, clan=toobig-7b)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/history/test_continuation_replay_hydration.py` file into multiple files? Use your best
%wait:toobig-7b.agent_scan_wire_markers.0
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

Split complete. All 20 tests pass in the new modules with the original import path preserved.

What changed (all ≤500 lines; was 956):

- [test_continuation_replay_hydration.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/history/test_continuation_replay_hydration.py:1) (67 lines) — now a facade with `__test__ = False` re-exporting `ORIGINAL_CONSTRAINT_SENTINEL` + all 20 `test_*` names, with `__all__` containing only public names.
- [_continuation_replay_hydration_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/history/_continuation_replay_hydration_helpers.py:1) (214 lines) — private module with public builders (`publish_agent_delta`, `publish_monitor`, `agent_member`, `monitor_member`, `write_agent_node`, `write_json`, `write_monitor_result_node`, `ORIGINAL_CONSTRAINT_SENTINEL`). Only this new file imports `_`-names, and only from the pre-existing `test_continuation_replay` module. Single-use `_tree_bytes` lives privately in the basic module instead.
- [test_continuation_replay_hydration_basic.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/history/test_continuation_replay_hydration_basic.py:1) (315 lines) — 7 core hydration tests.
- [test_continuation_replay_hydration_policy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/history/test_continuation_replay_hydration_policy.py:1) (288 lines) — 9 refusal/policy tests.
- [test_continuation_replay_hydration_retry.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/history/test_continuation_replay_hydration_retry.py:1) (268 lines) — 4 retry-splice tests.

No test patches `tests.history.test_continuation_replay_hydration.*` (only `sase.*` targets), so monkeypatch targets are unaffected.

Verified:

- `pytest` collect: 20 tests (7+9+4), 0 from facade; run: `20 passed`.
- Facade import check: `ORIGINAL_CONSTRAINT_SENTINEL` + sample tests import; `__test__ is False`, `__all__` has 21 public entries, no `_private` attrs.
- `ruff check` and `ruff format --check` on all 5 files: clean.
- `just _lint-mypy`: pass (`Success: no issues found`).
- `just _lint-toobig`: pass (exit 0; only info-level FYIs elsewhere).
- `just _lint-symvision` and `sase tool run check`: red, but only for `_runs` in `src/sase/agents_sync/v2_snapshot_io.py` and `src/sase/ace/tui/widgets/decks/final/overview_card.py` — files this split did not touch (`git status` shows only `tests/history/*`). Symvision scans `src/sase` only, so the split files contribute zero issues. I left the `src` failures unfixed as out of scope per the "fix files the split touched" instruction.
