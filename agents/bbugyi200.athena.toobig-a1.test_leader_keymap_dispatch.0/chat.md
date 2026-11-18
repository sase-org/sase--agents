# Chat History - ace-run (toobig-a1.test_leader_keymap_dispatch.0)

- **TIMESTAMP:** 2026-11-18 02:34:53 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a1.test_leader_keymap_dispatch.0

## Prompt

%auto
%id(test_leader_keymap_dispatch.0, clan=toobig-a1)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_leader_keymap_dispatch.py` file into multiple files? Use your best
%wait:toobig-a1.test_artifacts_beads_filtering.0
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

Split `test_leader_keymap_dispatch.py` (738 lines) into three modules with a facade:

- [test_leader_keymap_dispatch_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_leader_keymap_dispatch_launch.py) (262 lines): space/h/k/ctrl-space/r/R/x/X/H
- [test_leader_keymap_dispatch_navigation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_leader_keymap_dispatch_navigation.py) (289 lines): question/slash/g/j/J/L and repeat
- [test_leader_keymap_dispatch_system.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_leader_keymap_dispatch_system.py) (206 lines): y/u/U/E/at/ctrl+g
- [test_leader_keymap_dispatch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/test_leader_keymap_dispatch.py) (123 lines): facade with `__test__ = False`, re-exports all 50 public `test_` names
- [_leader_keymap_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/ace/tui/_leader_keymap_helpers.py) (255 lines): added public aliases `FakeApp`, `make_cs`, `BulkUnreadToggleResult` (plus related) so new modules never import `_`-prefixed names

Verified: `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig` each exit 0; 50/50 split tests pass; `sase tool run check` succeeded.
