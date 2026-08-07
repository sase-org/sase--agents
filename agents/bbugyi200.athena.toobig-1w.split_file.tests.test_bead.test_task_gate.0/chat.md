# Chat History - ace-run (toobig-1w.split_file.tests.test_bead.test_task_gate.0)

- **TIMESTAMP:** 2026-08-07 12:13:11 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1w.split_file.tests.test_bead.test_task_gate.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260807_110611.md`

## Prompt

#gh:sase-org/sase
%id:toobig-1w.split_file.tests.test_bead.test_task_gate.0
%clan(toobig-1w, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 878  tests/test_bead/test_task_gate.py[/bold #FFAF5F]
[#87D7FF]• 722  tests/test_linked_repo_sidecar_resolution.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_task_gate.py` file up into multiple files? Use your best judgement,
but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the shared helper and the split files.

I'll wait for the test run to report.

Waiting on `just install` + pytest to finish.

The split is written; I'm waiting on the verification run.

Still empty — waiting for the monitor to report.

I've finished writing the split and am waiting on the verification run to report before I confirm anything.

I'll stop polling and wait for the monitor notification.

I'll check the current state of the split files before committing.

All 27 tests are accounted for. Now running verification in this turn.

All 40 test cases pass. Now the lint gates.

Unrelated pre-existing flake (passes in isolation; my change only touched `tests/test_bead/`). Confirming lint gates:

Both failures are pre-existing and unrelated (the symvision one is a stale `--epic-symbol` for closed bead `sase-gz.4` in the justfile, which I didn't touch). Committing now.

Committed and pushed — working tree clean, branch level with `origin/master`.

## What I did

Split `tests/test_bead/test_task_gate.py` (880 lines) into five focused modules plus a shared helper:

| File | Lines | Covers |
|---|---|---|
| `test_task_gate.py` | 205 | gate construction, presentation, notifications |
| `test_task_gate_validation.py` | 231 | kind-contract validation, forgery rejection |
| `test_task_gate_actions.py` | 175 | launch/close/command dispatch |
| `test_task_gate_preview.py` | 157 | preview file rendering |
| `test_task_gate_snooze.py` | 156 | snooze duration parsing and deferral |
| `task_gate_test_helpers.py` | 21 | shared `task_triage_spec()` builder |

All well under the 500-line target. All 27 test functions (40 cases with parametrization) carried over unchanged, and I verified test-count parity against the pre-split file.

## Verification

- The five split files: **40 passed**.
- `just lint`: mypy clean on 2806 files; **fails** at the symvision gate on a stale `--epic-symbol 'sase-gz.4(resolve_notification_tab_icon)'` in the justfile for an already-closed bead. Pre-existing, from commit `94430f0f9`, in a file I didn't touch.
- `just check`'s scoped run: 26996 passed, 1 failed — `tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_Y_anchors_path_recovered_from_agent_meta_json`. It passes in isolation (13/13), so it's a parallel-run flake, unrelated to a test-only split under `tests/test_bead/`.

Neither failure is caused by this change, but per the project's discovered-work rule both warrant task beads — I did not file them, since the finalizer scoped this turn to committing. Worth filing: the stale epic-symbol entry (a hard lint block for every agent until removed) and the flaky artifact-modal test.
