# Chat History - ace-run (toobig-4j.workflow_executor_steps_prompt.0)

- **TIMESTAMP:** 2026-08-29 06:52:49 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-4j.workflow_executor_steps_prompt.0

## Prompt

%id:toobig-4j.workflow_executor_steps_prompt.0
%clan(toobig-4j, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 734  src/sase/xprompt/workflow_executor_steps_prompt.py[/#87D7FF]
[#87D7FF]• 729  tests/ace/tui/test_lazy_tier2_reconcile.py[/#87D7FF]
[#87D7FF]• 703  tests/test_workflow_executor.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/xprompt/workflow_executor_steps_prompt.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting the workflow executor file and how nearby xprompt modules are split, so the refactor stays consistent and each file stays under 500 lines.

The prompt-step file is 734 lines. Next I’ll map its functions and how sibling executor modules were split so the new files follow the same pattern.

I’ll read the related tests, the xprompt/lint notes, and the existing embedded-module split so the new files keep the same import surface.

There's a `toobig` lint gate — I'll check its exact file-size limit so the split lands cleanly under it.

I’ll split along the same lines as the embedded-workflow mixins: launch selection, output helpers, prompt preparation, and the remaining execute mixin—each file under 500 lines.

Format is rebuilding the Rust core binding first; I’ll wait for that to finish before running checks.

Format is clean. Next I’ll typecheck the new modules and run the prompt-step tests, then `just check`.

Symvision is flagging cross-module imports of underscore-prefixed helpers. I’ll read that lint note and rename the shared functions so they can be imported cleanly.

Cross-module helpers need public names for Symvision; I’ll rename those and keep true file-local helpers private.

Split `workflow_executor_steps_prompt.py` (734 lines) into four modules, each well under 500 lines, following the same pattern as the embedded-workflow mixins.

| File | Role | Lines |
|---|---|---|
| `workflow_executor_steps_prompt.py` | `PromptStepMixin` — agent invoke, HITL, post-steps | 392 |
| `workflow_executor_steps_prompt_prepare.py` | Prompt expansion / preprocessing mixin | 161 |
| `workflow_executor_steps_prompt_launch.py` | Model / provider launch selection | 163 |
| `workflow_executor_steps_prompt_outputs.py` | VCS diff, path fields, embedded output merge | 174 |

Callers of `PromptStepMixin` and `capture_vcs_diff` are unchanged: `workflow_executor_steps.py` still imports them from the original module. Helpers that are shared across files are public; file-local helpers stay private.

`just check` passed (lint including toobig/symvision, plus 117 scoped tests).
