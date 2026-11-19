# Chat History - ace-run (toobig-a6.test_agents_bead_warmup.0--plan)

- **TIMESTAMP:** 2026-11-18 19:06:08 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-a6.test_agents_bead_warmup.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: n40hd4aqzfmj
Inspect with: sase monitor show n40hd4aqzfmj
Monitor turn: toobig-a6.test_agents_bead_warmup.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19

Command:

```sh
just check
```

Reason:

Verify the bead-warmup test split before host completion


## Prompt

%id(test_agents_bead_warmup.0, clan=toobig-a6)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_agents_bead_warmup.py` file into multiple files? Use your best
%wait:toobig-a6.test_projected_detail_retention.0
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

I'll start by reading the split-related memory notes and the current test file so the split stays under 500 lines and preserves public imports.

The file is 793 lines. Next I’ll inspect its structure and how other ACE TUI tests were split so this split can match that pattern.

I’ll follow the fleet-refresh split: a `__test__ = False` facade, public helpers in a private module, and focused test modules under 500 lines.

Files are in place. Next I’ll format them, confirm line counts, and run the split tests.

The split files are clean; remaining lint failures are in other files. I’ll get the final-context template and start prepared verification.

Prepared completion covers the dirty repo, so I don’t need to submit a declaration. Cleaning up the wrapper, then I’ll summarize the split.

Split `tests/ace/tui/test_agents_bead_warmup.py` (793 lines) into five files, each well under 500 lines.

**Layout**
- `test_agents_bead_warmup.py` — facade; re-exports public tests and `WarmupProbe`; `__test__ = False` so pytest does not collect twice
- `_agents_bead_warmup_helpers.py` — shared public helpers (`FakeApp`, `make_agent`, `confirmed_lookup`, `clear_bead_display_cache`)
- `test_agents_bead_warmup_schedule.py` — scheduling, coalescing, candidate scope
- `test_agents_bead_warmup_results.py` — off-thread compute and in-place apply (`_issue_payload` stays private here)
- `test_agents_bead_warmup_run.py` — async worker and Textual pump (`_PumpResponsiveApp` stays private here)

Helpers used by more than one module have public names in the private helpers module. No `_`-prefixed names are imported across the new modules. Production monkeypatch targets are unchanged.

**Checks**
- 29 tests passed
- `just _lint-symvision` passed
- `just _lint-mypy` is red in `src/sase/axe/_chop_batch_recovery_observations.py` (untouched)
- `just _lint-toobig` is red in `tests/axe/test_axe_chop_batch_recovery.py` (untouched)

`just check` is staged as monitor `n40hd4` and will run after this turn; on green the host commits `test(ace): split test_agents_bead_warmup into focused modules`.
