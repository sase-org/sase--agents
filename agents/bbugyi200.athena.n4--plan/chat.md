# Chat History - ace-run (n4--plan)

- **TIMESTAMP:** 2026-07-28 11:56:26 EDT
- **MODEL:** claude/opus
- **AGENT:** n4--plan

**Plan:** /home/bryan/.sase/plans/202607/ctrl_space_prompt_guard.md


## Prompt

#gh:gh_sase-org__sase Can you help me make the `<ctrl+space>` keymap not work in the prompt input widget? Leaving this keymap enabled allows the user to accidentally wipe out their current prompt. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/ctrl_space_prompt_guard.md`

> # Plan: Make Ctrl+Space inert while a prompt input bar is open
> ## Problem
> `Ctrl+Space` is bound at app level to `start_agent_from_changespec` ("Repeat last +/Ctrl+Space selection"). While the
> user is typing a prompt in the prompt input bar, an accidental `Ctrl+Space` destroys that prompt.
> Root cause chain (all paths verified by reading the code):
> 1. `src/sase/ace/tui/bindings.py:157` registers
>    `Binding("ctrl+@", "start_agent_from_changespec", "Run Agent (PR)", show=False)`, and
>    `src/sase/default_config.yml:282` sets the same default key. `ctrl+@` is Textual's canonical name for Ctrl+Space
>    (`Keys.ControlSpace` aliases to `ctrl+@`; the repo's own `src/sase/ace/tui/keymaps/key_validation.py:53-56`
>    normalizes `ctrl+space` / `ctrl+at` to `ctrl+@`).

*See full plan file for details.*

