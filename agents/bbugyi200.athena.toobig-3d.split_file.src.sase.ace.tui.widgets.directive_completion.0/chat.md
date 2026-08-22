# Chat History - ace-run (toobig-3d.split_file.src.sase.ace.tui.widgets.directive_completion.0)

- **TIMESTAMP:** 2026-08-22 01:18:17 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-3d.split_file.src.sase.ace.tui.widgets.directive_completion.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260821_185258.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.ace.tui.widgets.directive_completion.0, clan=toobig-3d)
%wait:toobig-3d.split_file.src.sase.ace.tui.widgets._prompt_input_bar_stack_rendering.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/ace/tui/widgets/directive_completion.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I’ll map the widget’s responsibilities, extract cohesive pieces while preserving its public imports, then run the repository’s required checks. I’ll use the requested `/sase_final` skill as the last action before I report back.

The file is 829 lines and naturally separates into four areas: public orchestration, shared metadata/row adapters, agent target completion, and model completion. I’m checking import and test boundaries now so the split stays source-compatible.

The split is in place: the public facade is now 232 lines, with agent, catalog/core-row, model, and metadata modules ranging from 98–308 lines. The existing public import surface—and the model-catalog test patch point—remain intact. I’m moving through focused tests and the required whole-repo verification now.

The local install is rebuilding the Rust binding in this fresh workspace; it’s still progressing normally. Once that completes, I’ll run the directive-completion suite and `just check`.

The focused suite is at 109/110 passing. The one failure is a directive-contract parity assertion where `%final` disappeared only after earlier tests; I’m isolating it now to determine whether this is shared test state or a regression from the module move.

Formatting and type checking are clean. `just check` has passed its formatting, Ruff, mypy, feature-flag, script, wait-policy, changelog, and terminology gates; the remaining repository checks are still running.

`just check` found one architectural lint issue in the new model helper: it imported a private catalog entry type solely for annotation. The project’s Symvision rules apply here, so I’m using `/sase_memory_read` now to follow the required remediation guidance before adjusting that annotation.

The Symvision issue is resolved by keeping the private model entry type behind its owning module boundary. The rerun has now passed Symvision and the size gate as well; the scoped tests are the remaining `just check` phase.

The full scoped run passed 2,397 tests and exposed two consistent `%final` name-completion failures. The Python refactor’s candidate call is unchanged, so I’m tracing the shared Rust contract boundary next. Because that implementation lives in the linked `sase-core` repository, project policy requires me to use `/sase_repo` before inspecting it.

This is confirmed baseline drift, not a refactor regression: the checked-in Rust core explicitly hides `%final`, while two later Python tests require it, and the old Python function made the same core call. Project policy says confirmed unrelated test failures should be recorded, so I’m using `/sase_new_task` to deduplicate and capture this CI issue before finishing verification of the refactor itself.

The failure already has an owning active epic (`sase-s0`, “Beautiful and reliable final directive completion”), with multiple matching reports, so I added this independent reproduction there instead of creating a duplicate task. I’m now running the complete affected completion set with only those two known baseline assertions deselected, then I’ll do a final diff/API audit.

Implementation and verification are complete: all five directive-completion files are under 500 lines, the public facade exports are intact, and the affected suite passes 141 tests with only the two documented baseline `%final` assertions deselected. I’m invoking the requested `/sase_final` declaration now; after a successful submission I won’t make further repository changes.

Implemented the split while preserving the existing public API:

- [directive_completion.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/widgets/directive_completion.py) — 232-line facade
- `_directive_completion_candidates.py` — 308 lines
- `_directive_completion_models.py` — 174 lines
- `_directive_completion_agents.py` — 117 lines
- `_directive_completion_types.py` — 98 lines

Verification:

- 141 affected tests passed.
- Formatting, Ruff, mypy, Symvision, validation, and size gates passed.
- Full scoped run: 2,397 passed; two unrelated `%final` baseline failures were recorded on existing epic `sase-s0`.
- Final commit declaration accepted as `refactor(ace): split directive completion helpers`.
