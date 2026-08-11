# Chat History - ace-run (toobig-2f.split_file.src.sase.main.patch_handler.0--plan)

- **TIMESTAMP:** 2026-08-11 11:49:03 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-2f.split_file.src.sase.main.patch_handler.0--plan
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260811_110152.md`

**Plan:** /home/bryan/.sase/plans/202608/split_patch_handler.md


## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.main.patch_handler.0, clan=toobig-2f)
%wait:toobig-2f.split_file.src.sase.ace.tui.modals.wait_modal.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/main/patch_handler.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/split_patch_handler.md`

> # Split the patch command handler into focused modules
> Refactor `src/sase/main/patch_handler.py`, currently about 750 lines, into cohesive
> command modules while preserving CLI behavior, compatibility imports, and test seams.
> Keep every resulting Python source file at or below 500 lines.
> ## Implementation
> 1. Keep `sase.main.patch_handler` as the command-dispatch facade. Preserve
>    `handle_patch_command`, the currently exported private handlers, and compatibility
>    globals used by tests or callers. Its wrapper functions should delegate without
>    changing exit codes, stdout/stderr text, JSON payloads, or the legacy
>    `sase changespec` facade.

*See full plan file for details.*

