# Chat History - ace-run (toobig-9j.project_display_names.0)

- **TIMESTAMP:** 2026-11-06 14:48:33 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9j.project_display_names.0

## Prompt

%id:toobig-9j.project_display_names.0
%clan(toobig-9j, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 743  tests/test_axe_chop_output_contract_retention.py[/#87D7FF]
[#87D7FF]• 706  src/sase/project_display_names.py[/#87D7FF]
[#87D7FF]• 706  tests/test_run_agent_runner_notifications.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/project_display_names.py` file into multiple files? Use your best
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

I'll start by reading the source file, the split constraints, and the lint/test notes so the split stays under 500 lines without breaking public imports.

I’ll inspect similar module splits and every test that patches private names so the facade keeps those monkeypatch targets working.

I'll split the module into snapshot, cache, and labels files, then keep a thin public facade that re-exports the original names.

`unambiguous_folded_refs` is only used in this file, so I’ll keep it private to satisfy Symvision.

Next I’ll retarget tests so monkeypatches hit the cache and labels modules instead of the facade.

Formatter is done. Next I’ll run the three requested lints on the split files.

Symvision flagged a stale pragma on `humanize_safe_stem` because the facade now imports it. I’ll remove that comment and re-run the lint.

The three requested lints passed. Next I’ll run `sase tool run check`.

I'll wait for the in-progress `sase tool run check`, then finish verification and declare. Checking the command and the skills I need next.

Check is still in later stages. I'll wait it out and pull lint/test memory plus the log tail in parallel.

The log is still sitting after committed plans; I'll inspect the tool-run status and whether pytest is actually running.

Scoped tests are still running. I'll keep waiting on that check.

Check failed on remaining `list_project_records` monkeypatches against the facade. I'll retarget those seams and inspect the other failures.

The remaining failures patch `list_project_records` on the facade. I'll find every leftover seam and retarget it.

I'll retarget the two leftover `list_project_records` patches and check the by-name importer list.

I'll retarget the leftover `list_project_records` seams onto `_project_display_cache`.

I'll run the previously failing tests first, then the required lints and the full check.

Those five tests passed. Next I’ll run the three required lints, then `sase tool run check`.

Lints are green. Starting `sase tool run check`.

Check failed on a transient PyPI DNS error during SASE validation. Retrying the same gate.

Check passed. Gathering the finalizer context and preparing the commit declaration.

I'll write the commit manifest and submit the final declaration.

Split `src/sase/project_display_names.py` into a thin public facade plus three private modules, each under 500 lines:

| File | Lines | Role |
|---|---|---|
| `src/sase/project_display_names.py` | 67 | Public facade; original `__all__` re-exports |
| `src/sase/_project_display_snapshot.py` | 181 | Snapshot types and ref lookup |
| `src/sase/_project_display_cache.py` | 296 | Inventory cache, freshness, humanize memo |
| `src/sase/_project_display_labels.py` | 222 | Display maps and humanize helpers |

`sase.project_display_names` still exposes the original public API. Shared helpers used by more than one module are public names inside the private `_project_display_*` modules (`cached_project_display_snapshot`, `humanize_cl_name_cached`). Tests that patched imported seams (`list_project_records`, cache dicts) now target `_project_display_cache`.

Verification:
- `just _lint-toobig`, `just _lint-mypy`, and `just _lint-symvision` all passed
- `sase tool run check` passed (`a8169820df1420abfb6cf25021718ff7`) after a retry of a transient PyPI DNS failure on SASE validation
