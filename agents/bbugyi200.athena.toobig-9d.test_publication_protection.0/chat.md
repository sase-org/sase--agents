# Chat History - ace-run (toobig-9d.test_publication_protection.0)

- **TIMESTAMP:** 2026-11-04 19:40:01 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9d.test_publication_protection.0

## Prompt

%id:toobig-9d.test_publication_protection.0
%clan(toobig-9d, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 909  tests/test_agent_hijack_recover.py[/bold #FFAF5F]
[#87D7FF]• 834  tests/agents_sync/test_publication_job.py[/#87D7FF]
[#87D7FF]• 747  tests/agents_sync/test_publication_protection.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agents_sync/test_publication_protection.py` file into multiple files? Use your best
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

Split `tests/agents_sync/test_publication_protection.py` (747 lines) into a package preserving its import path:

- [test_publication_protection/__init__.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_publication_protection/__init__.py): facade re-exporting the 10 public `test_*` names, no `_private` names.
- [test_publication_protection/_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_publication_protection/_helpers.py:1) (414 lines): shared builders with public names `install_fake_core`, `install_fake_scanner`, `seed_stale_openai_block`, copied verbatim from the original helpers.
- [test_publication_protection/test_scan_staging.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_publication_protection/test_scan_staging.py:1) (139 lines): clean/hit/non-clean staging.
- [test_publication_protection/test_scanner_resilience.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_publication_protection/test_scanner_resilience.py:1) (110 lines): exception, missing binding, oversized, symlink.
- [test_publication_protection/test_ledger_rescan.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_publication_protection/test_ledger_rescan.py:1) (171 lines): transient resolve and stale-block rescan/reblock.

No new module imports a `_`-prefixed symbol: private `sase.agents_sync._publication_protection_*` access is via string `monkeypatch.setattr` targets, and the ledger read was retargeted to public `publication_protection.read_publication_protection_ledger_from_path`. Sibling imports are only public names from the private `_helpers` module.

Verification:
- `pytest tests/agents_sync/test_publication_protection/`: 11 passed.
- `just _lint-symvision`: pass.
- `just _lint-mypy`: no issues in 6376 files.
- `just _lint-toobig`: pass (only pre-existing warning in `tests/test_agent_hijack_recover.py`).
- `sase tool run check`: all lint stages pass; test stage 1124 passed, 1 failed but triaged `KNOWN` (`test_macro_string_literals_avoid_xprompt_terms`, unrelated), verdict `no_new_failures`.

Declaration submitted: split of `test_publication_protection` committed via finalizer.
All 11 tests passed via the package import path. No files were changed.
