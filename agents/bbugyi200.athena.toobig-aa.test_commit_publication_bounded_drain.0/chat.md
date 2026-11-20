# Chat History - ace-run (toobig-aa.test_commit_publication_bounded_drain.0)

- **TIMESTAMP:** 2026-11-20 07:11:59 EST
- **MODEL:** claude/opus
- **AGENT:** toobig-aa.test_commit_publication_bounded_drain.0

## Prompt

%id(test_commit_publication_bounded_drain.0, clan=toobig-aa)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agents_sync/test_commit_publication_bounded_drain.py` file into multiple files? Use your best
%wait:toobig-aa.test_skill_uses_loader.0
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

I'm splitting the 732-line test file into a few smaller ones. First I'm checking existing helper conventions and anything that imports the original module.

Nothing else imports the module. The flake baseline lists one test by node ID, so that test stays in the original file. Now writing the shared helper module and the two new test modules.

Next, the budget/timer module.

Now rewriting the original file to keep only the render-timeout and retry tests.

`cp` is aliased to interactive mode here, so I'll redo that step with `command cp -f`. The original file wasn't touched.

All test bodies match the originals exactly. Next: formatting, ruff, and the three split test files under pytest.

zsh doesn't word-split `$F`, so I'll pass the file list as an array.

All 14 tests pass. Next, the three lint gates you asked for, one at a time.

Symvision flags `OutboxGroup` in `src/sase/doctor/_agent_publication.py`. My change only touches test files, and Symvision ignores tests, so I'm checking whether this failure already existed.

That failure is already on master in a file the split doesn't touch: `OutboxGroup` is only used inside its own file, and the tree was clean when I started. I'll leave it. Next, mypy and toobig.

mypy and toobig both pass, and the original file no longer shows up in toobig's 700-line info list. Next: `sase tool run check`.

The causing commit came from phase `sase-1tz.2.1.7`. Next I'm checking whether epic `sase-1tz.2.1` is still in progress and whether it already records this finding.

I recorded it on the causing epic and didn't create a task. Last step: the final declaration.

I split `tests/agents_sync/test_commit_publication_bounded_drain.py` (732 lines) into four files, each under 500 lines. All 14 tests pass, and the commit is queued for after this turn.

| File | Lines | Contents |
|---|---|---|
| `test_commit_publication_bounded_drain.py` (original path) | 369 | Render-timeout and retry tests: blocked render, manifest timeout, later-drain retry, young `index.lock`, inventory slice. Keeps `_publish_readme`, since only this file uses it. |
| `test_commit_publication_bounded_drain_cleanup.py` | 229 | Cleanup tests: both path families, cleanup failure attached as a note, stalled cleanup, empty-drain scratch sweep, ledger deferred/failed results. |
| `test_commit_publication_bounded_drain_budget.py` | 157 | Timer and budget tests: alarm-timer restore, cumulative budget cap, `_drain_work_timeout` reserve, reserve left for cleanup. |
| `_commit_publication_bounded_drain_helpers.py` | 32 | `configure_target` (was `_configure_target`), public inside this private module because all three test files use it. |

- **Behavior:** an AST comparison against the original shows every test body is identical, apart from the call to the renamed helper.
- **Imports and patches:** nothing outside this file imported the original module, so no facade was needed. No `_`-prefixed name is imported between the new files. Monkeypatch targets are unchanged.
- **Flake baseline:** the one node ID listed in `tests/reproducible_flake_baseline.txt` stays at its original path.

**Checks:**
- `just _lint-mypy`: passes.
- `just _lint-toobig`: passes, and the original file no longer appears in its 700-line warnings.
- `just _lint-symvision`: fails on `OutboxGroup` in `src/sase/doctor/_agent_publication.py`. That file isn't part of the split, and the same failure is on master.
- `sase tool run check`: exits 1 with verdict `no_new_failures`. The only failed stage is that same `OutboxGroup` finding, labeled KNOWN, and the scoped tests passed. Run ID `784e83170d0b44d809b995f8594f8b33`.

`OutboxGroup` is used only inside its own file. It was added by phase `sase-1tz.2.1.7` of epic `sase-1tz.2.1`, which is still in progress and already tracks this failure. I added a note there confirming it's still failing on the current master instead of opening a duplicate task. The fix is to rename it to `_OutboxGroup`.
