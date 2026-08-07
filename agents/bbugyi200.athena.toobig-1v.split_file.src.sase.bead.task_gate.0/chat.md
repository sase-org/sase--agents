# Chat History - ace-run (toobig-1v.split_file.src.sase.bead.task_gate.0)

- **TIMESTAMP:** 2026-08-07 00:00:08 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1v.split_file.src.sase.bead.task_gate.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260806_230235.md`

## Prompt

#gh:sase-org/sase
%id:toobig-1v.split_file.src.sase.bead.task_gate.0
%clan(toobig-1v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 952  tests/test_axe_chop_bead_task_triage.py[/bold #FFAF5F]
[#87D7FF]• 771  src/sase/bead/task_gate.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/bead/task_gate.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the split modules.

Now the facade:

Now let me install and run the checks.

While that runs, let me review the diff for correctness.

Pre-existing on clean master — not from my change. Now the final full gate:

`just check-full` is green. Let me file the pre-existing visual-snapshot failure as a task bead.

Done. `src/sase/bead/task_gate.py` (771 lines) is now five modules, largest 231 lines:

| File | Lines | Holds |
|---|---|---|
| `task_gate.py` | 129 | Front door: `create_task_triage_gate` + re-exports/`__all__` |
| `_task_gate_spec.py` | 231 | Constants, `build_task_triage_gate_spec`, `close_record_payload`, result schema, option command wrapper + entrypoint |
| `_task_gate_preview.py` | 174 | Markdown preview, presentation note, close-history callout, +1 evidence |
| `_task_gate_response.py` | 156 | `TaskTriageResponse`, `translate_task_triage_response`, feedback validation |
| `_task_gate_actions.py` | 210 | `cancel`/`launch`/`close`/`snooze` host effects, pending-gate lookup, `bead_gate_actor` |

Naming follows the existing `_db_*` / `_project_*` / `_sync_*` convention in `src/sase/bead/`. Import direction is acyclic: `preview ← spec ← response ← actions ← task_gate`.

Two things the split forced, both deliberate:

- **`_TaskTriageResponse` → `TaskTriageResponse`** and **`_build_task_triage_gate_spec` → `build_task_triage_gate_spec`**. Symvision forbids importing private symbols across files, and both are now consumed across module boundaries. `TaskTriageResponse` is exported from the facade; the spec builder is not (it's internal, imported directly by the two tests that use it).
- **The persisted command script text is unchanged** — it still reads `from sase.bead.task_gate import execute_task_triage_gate_command`. That string is written into every gate bundle and revalidated byte for byte, so the facade re-export keeps existing pending gates valid. There's a comment on `task_triage_gate_command_script` saying so.

Test updates were mechanical: 5 `patch()` targets for `_resolve_task_triage_project_cwd` retargeted to `sase.bead._task_gate_actions`, plus `_find_pending_task_triage` and the spec-builder imports.

**Verification:** `just check-full` is green (all lint gates + 26720 tests passing).

One unrelated finding: `just test-visual` fails on `test_artifacts_beads_reopened_detail_png_snapshot` — a 515-pixel diff that is exactly the new `z snooze` footer chip. I reproduced it on clean master with my tree stashed, so it isn't mine; commit `0f7960d08` added the chip without refreshing that golden. Since epic `sase-gn` is in progress and owns that commit, I recorded it as a `DISCOVERED ISSUE:` note on `sase-gn` (with the diff PNG as artifact `file:explicit:bd71db24c9d2d1e831611af5`) rather than filing a separate task. The fix is a one-snapshot golden refresh; note that `test-visual` runs neither in `just check` nor `just check-full`.

`just check` is green. Committing now.

Committed as `b8a9fb4ed`; working tree is clean and `master` is level with `origin/master`.

**What landed:** `src/sase/bead/task_gate.py` (771 lines) split into five modules, largest 231 lines.

| File | Lines | Holds |
|---|---|---|
| `task_gate.py` | 129 | Facade: `create_task_triage_gate` + re-exports/`__all__` |
| `_task_gate_spec.py` | 231 | Constants, `build_task_triage_gate_spec`, `close_record_payload`, result schema, option command wrapper |
| `_task_gate_preview.py` | 174 | Markdown preview, presentation note, close-history callout, +1 evidence |
| `_task_gate_response.py` | 156 | `TaskTriageResponse`, response translation, feedback validation |
| `_task_gate_actions.py` | 210 | cancel/launch/close/snooze host effects, pending-gate lookup, `bead_gate_actor` |

Naming follows the existing `_db_*` / `_project_*` / `_sync_*` convention in `src/sase/bead/`. Import direction is acyclic: `preview ← spec ← response ← actions ← task_gate`.

Two deliberate consequences of the split:

- **`_TaskTriageResponse` → `TaskTriageResponse`** and **`_build_task_triage_gate_spec` → `build_task_triage_gate_spec`** — Symvision forbids cross-module private imports, and both are now consumed across boundaries. The response type is re-exported from the facade; the spec builder stays internal.
- **The persisted gate command script text is unchanged.** It still reads `from sase.bead.task_gate import execute_task_triage_gate_command` — that string is written into every gate bundle and revalidated byte for byte, so the facade re-export keeps existing pending gates valid. There's a comment on `task_triage_gate_command_script` recording this.

Test changes were mechanical: retargeted `patch()` paths and imports across four test files.

**Verification:** `just check` re-run in this pass — all lint gates and the scoped test lane green (68 of 2382 test files selected).

One caveat I want to be straight about: the earlier `just check-full` run happened in a prior pass that I can't re-confirm from here, and I ran only `just check` this time. The change is import-graph-shaped, so the scoped selection should cover it, but a full-suite run has not been independently confirmed in this pass.

Also unrelated and still open: `just test-visual`'s `test_artifacts_beads_reopened_detail_png_snapshot` fails on a 515-pixel diff that is exactly the new `z snooze` footer chip from commit `0f7960d08`. It reproduces on clean master, so it predates this work; it's recorded as a `DISCOVERED ISSUE:` note on the in-progress epic `sase-gn` that owns that commit. The fix is a one-snapshot golden refresh. Note `test-visual` runs in neither `just check` nor `just check-full`.
