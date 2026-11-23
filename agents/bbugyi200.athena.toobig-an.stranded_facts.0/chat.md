# Chat History - ace-run (toobig-an.stranded_facts.0)

- **TIMESTAMP:** 2026-11-23 11:30:20 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-an.stranded_facts.0

## Prompt

%id:toobig-an.stranded_facts.0
%clan(toobig-an, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 795  src/sase/bead/stranded_facts.py[/#87D7FF]
[#87D7FF]• 749  src/sase/ace/tui/actions/agents/_archive_controller_build.py[/#87D7FF]
[#87D7FF]• 702  tests/ace/tui/test_agents_bead_warmup_results.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/bead/stranded_facts.py` file into multiple files? Use your best
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

I'll split `stranded_facts.py` into modules of 500 lines or fewer while keeping the public import path and behavior. First I'll read the split rules, the source file, and how tests import it.

The source is large, so I’ll map its structure, existing split patterns, and the tests that monkeypatch it.

I'll read the rest of the source, the lint/split conventions, and a similar package split so the new modules match this repo.

I’ll inspect test monkeypatches and a comparable facade split so public names stay stable.

I’ll add a thin facade and focused private modules, then retarget tests so monkeypatches hit the defining modules.

Writing the split modules next: a public facade plus private snapshot, member, bead, and collect files.

Retargeting tests to the modules that define or look up each patched name.

Formatting is clean. Next I’ll run the three requested lints one by one, then `sase tool run check`.

The three lints passed. I’ll run the stranded-work tests first, then `sase tool run check`.

The stranded-work tests passed. Starting `sase tool run check` next.

Check succeeded. I’ll gather the host finalizer context and submit the commit declaration.

Split `src/sase/bead/stranded_facts.py` into focused modules while keeping the public import path.

`sase.bead.stranded_facts` is now a facade that re-exports:

- `collect_issue_titles`
- `collect_stranded_work_input`
- `collect_stranded_work_snapshot`

Implementation lives in private modules with public helper names only where more than one module needs them:

| File | Role | Lines |
|---|---|---|
| `stranded_facts.py` | Public facade | 30 |
| `_stranded_facts_collect.py` | Collectors | 74 |
| `_stranded_facts_snapshot.py` | Snapshot reuse and batched index reads | 217 |
| `_stranded_facts_beads.py` | Per-bead payload assembly | 176 |
| `_stranded_facts_members.py` | Member lifecycle, liveness, staged handoff | 360 |

Tests that patched or called former private names on the facade now target the defining modules (`_stranded_facts_snapshot`, `_stranded_facts_collect`, `_stranded_facts_beads`, `_stranded_facts_members`).

Verification:

- `just _lint-symvision` passed
- `just _lint-mypy` passed
- `just _lint-toobig` passed
- `sase tool run check` succeeded (run `20042138b2e2d2bea4de5d86adb57bf6`)
