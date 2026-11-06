# Chat History - ace-run (toobig-9l.test_agent_hijack_recover_release.0)

- **TIMESTAMP:** 2026-11-06 18:08:37 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9l.test_agent_hijack_recover_release.0

## Prompt

%id(test_agent_hijack_recover_release.0, clan=toobig-9l)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_agent_hijack_recover_release.py` file into multiple files? Use your best
%wait:toobig-9l.preview.0
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

I'll start by reading the split-file conventions and the current test module so I can plan a clean, behavior-preserving split.

I'll load the lint notes and measure the test file so the split follows project conventions.

The file is 422 lines, so I’ll read the whole module and a recent sibling split to match that pattern.

I'll inspect the support module and a recent class-based split so the new files follow the same public-path and helper rules.

I have a clean split: three focused test modules plus a facade that keeps the original public import path. Next I’ll write those files and check the finalizer skill.

I’ll write the three focused test modules and turn the original file into a compatibility facade.

Files are in place. I’ll format them, then run the three requested linters.

Formatting is clean. Next I’ll run the three linters one at a time, starting with Symvision.

Symvision is clean. I’ll run mypy next, then the toobig line-count gate.

The three linters passed. I’ll run the split tests first, then the full `sase tool run check`.

All 12 tests passed without double collection. Next is the full `sase tool run check`.

Check succeeded. I’ll collect the finalizer context and submit the commit declaration.

Split `tests/test_agent_hijack_recover_release.py` along the three test classes, and kept the original import path as a facade.

**New modules** (all under 500 lines):
- `tests/test_agent_hijack_recover_release_cli.py` — `TestReleaseCli`
- `tests/test_agent_hijack_recover_release_kill_restart.py` — `TestKillRestartHijackRouting`
- `tests/test_agent_hijack_recover_release_persist.py` — `TestPersistRecoverRelease`
- `tests/test_agent_hijack_recover_release.py` — compatibility facade with `__test__ = False`

The facade re-exports the three public test classes plus the original module’s public helper and domain names. Private methods (`_preview`, `_request`) stayed in the module that uses them. Shared helpers already live as public names in `tests/_agent_hijack_recover_release_support.py`. Monkeypatch targets still point at production modules.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — pass
- 12 split tests passed
- `sase tool run check` — succeeded
