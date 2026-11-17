# Chat History - ace-run (toobig-9w.test_agent_hijack_stop.0)

- **TIMESTAMP:** 2026-11-17 02:03:21 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9w.test_agent_hijack_stop.0

## Prompt

%auto
%id(test_agent_hijack_stop.0, clan=toobig-9w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_agent_hijack_stop.py` file into multiple files? Use your best
%wait:toobig-9w.test_agent_hijack_latch.0
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

I'll start by reading the split rules, the current test file, and the lint notes so the new modules stay under 500 lines without changing behavior.

The file is 816 lines, so I’ll read the lint notes, any prior split patterns, and the test module next.

I’ll look at how similar test modules were split so this one matches the same facade and helper pattern.

I’ll split along the original groups: shared helpers in a private support module, then eligibility, outcomes, CLI, and persist tests behind a facade.

`hijack_ids` is only used by eligibility tests, so I’ll move it into that module and keep `TS` private in support.

All split files are under 500 lines. Next I’ll format them and run the three requested lints.

The imported fixture was colliding with the test parameter. I’ll follow the latch pattern and expose it as `shared_hijack_home` with fixture name `hijack_home`.

Symvision and mypy passed. toobig only failed on an untouched file, so I’ll run the split tests next, then `sase tool run check`.

The split tests passed. I’ll run `sase tool run check` in the foreground next.

`sase tool run check` succeeded. I’ll gather the finalizer context and submit the declaration.

Split `tests/test_agent_hijack_stop.py` (816 lines) into focused modules, each well under 500 lines. The original import path still works through a facade that re-exports public names only.

**Layout**
- `tests/test_agent_hijack_stop.py` — facade (`__test__ = False`) so tests are not collected twice
- `tests/_agent_hijack_stop_support.py` — shared public helpers (`make_artifacts`, `stop_deps`, `shared_hijack_home`, …)
- `tests/test_agent_hijack_stop_eligibility.py` — refusals, redirects, re-resolution
- `tests/test_agent_hijack_stop_outcomes.py` — held / finished-first / stop-blocked
- `tests/test_agent_hijack_stop_cli.py` — `sase agent hijack`
- `tests/test_agent_hijack_stop_persist.py` — `sase ops agent persist-hijack`

Helpers used by more than one module live as public names in the private support module. `_hijack_ids` stayed private in eligibility, the only consumer. Monkeypatch targets still point at production modules.

**Verification**
- 23 tests passed (same count as before)
- `just _lint-symvision` and `just _lint-mypy` passed
- `just _lint-toobig` failed on untouched `tests/ace/tui/test_artifacts_post_paint_publication.py` (1201 lines); every split file is under 250 lines
- `sase tool run check` succeeded
