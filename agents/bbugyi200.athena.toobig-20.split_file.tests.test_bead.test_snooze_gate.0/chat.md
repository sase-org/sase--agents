# Chat History - ace-run (toobig-20.split_file.tests.test_bead.test_snooze_gate.0)

- **TIMESTAMP:** 2026-08-08 00:25:12 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-20.split_file.tests.test_bead.test_snooze_gate.0

## Prompt

#gh:sase-org/sase
%id:toobig-20.split_file.tests.test_bead.test_snooze_gate.0
%clan(toobig-20, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 778  tests/test_bead/test_snooze_gate.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_bead/test_snooze_gate.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Clear precedent exists (`test_task_gate*.py` + `task_gate_test_helpers.py`). I'll mirror that shape.

Now the four test files:

Split done — all 53 tests still pass (same count as before) and `just check` is green.

The 778-line file became four test modules plus a shared helper, mirroring the existing `test_task_gate*.py` / `task_gate_test_helpers.py` convention in the same directory:

| File | Lines | Contents |
|---|---|---|
| `tests/test_bead/snooze_gate_test_helpers.py` | 75 | `WAKE_TIME`, `snooze_record()`, `bead_snooze_spec()`, `preview_resource()`, `mutation_double()` |
| `tests/test_bead/test_snooze_gate.py` | 208 | Canonical spec + snoozed-notification contract, presentation note, preview rendering, +1 evidence |
| `tests/test_bead/test_snooze_gate_validation.py` | 208 | Auto-resolution refusal, forged-contract table, legacy/blank-notes acceptance, preview injection |
| `tests/test_bead/test_snooze_gate_actions.py` | 264 | Close / Ready / re-snooze host effects, duration rejection, translation, command stdin rejection |
| `tests/test_bead/test_snooze_time.py` | 79 | `parse_snooze_request` / `parse_snooze_until` parsing forms |

Two notes on judgement calls:

- The private-helper names lost their leading underscores when they moved into the shared module (`_spec` → `bead_snooze_spec`, `_snooze` → `snooze_record`), matching `task_triage_spec` next door. Helpers used by only one module (`_resnooze`, `_blank_notes_spec_with_evidence`) stayed private in that module.
- The duration-parsing tests were only incidentally in the gate file; they test `sase.bead.snooze_time` directly, so they got their own file named after the module under test rather than being folded into a gate file.

I'll commit the split with the sase commit skill.

Committed and pushed as `c0e27a7a8`; working tree is clean and `master` is level with `origin/master`.

The 778-line `tests/test_bead/test_snooze_gate.py` is now five modules, mirroring the neighboring `test_task_gate*.py` / `task_gate_test_helpers.py` convention:

| File | Lines | Contents |
|---|---|---|
| `snooze_gate_test_helpers.py` | 75 | `WAKE_TIME`, `snooze_record()`, `bead_snooze_spec()`, `preview_resource()`, `mutation_double()` |
| `test_snooze_gate.py` | 208 | Canonical spec + snoozed-notification contract, presentation note, preview rendering |
| `test_snooze_gate_validation.py` | 208 | Auto-resolution refusal, forged-contract table, legacy/blank-notes acceptance, preview injection |
| `test_snooze_gate_actions.py` | 264 | Close / Ready / re-snooze host effects, duration rejection, translation, command stdin rejection |
| `test_snooze_time.py` | 79 | `parse_snooze_request` / `parse_snooze_until` parsing forms |

Two judgement calls worth flagging: helpers promoted to the shared module dropped their leading underscores (`_spec` → `bead_snooze_spec`) to match `task_triage_spec` next door, while single-consumer helpers stayed private in place; and the duration-parsing tests exercise `sase.bead.snooze_time` directly, so they got a file named after the module under test rather than being folded into a gate file. No test bodies changed.
