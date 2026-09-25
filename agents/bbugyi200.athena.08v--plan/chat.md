# Chat History - ace-run (08v--plan)

- **TIMESTAMP:** 2026-08-20 14:37:29 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 08v--plan

**Plan:** /home/bryan/.sase/plans/202608/targeted_mini_xprompt.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support for a new keymap that makes it easier for users to
create a single-prompt (i.e. not an xprompt swarm) xprompts from the prompt input
widget?

- We should add a new "targeted mini-xprompt" mode to support this functionality.
- We already support a "targeted xprompt" mode which targets the entire prompt input
  widget stack.
- The difference with this mode is that we will only target a single prompt input
  widget.
- Changes to existing keymaps:
  - As a part of this change, let's migrate the `<ctrl+g>X` (insert) / `gX` (normal)
    keymaps, which allow the user to create a new local xprompt, in the prompt input
    widget to `<ctrl+g>L` and `gL`.
  - We should then migrate the `<ctrl+g>x` (insert) / `gx` (normal) keymaps to
    `<ctrl+g>X` / `gX`.
- The `<ctrl+g>x` / `gx` keymaps should then be deligated to this new "targeted
  mini-xprompt" mode.
- These keymaps should trigger a prompt for a new xprompt name with live completion for
  existing xprompts.
- We should support creating a new xprompt (by typing in an unused xprompt name) and
  editing existing xprompts (by typing in / selecting an existing xprompt name).
- This feature should take inspiration from the existing "targeted snippet" prompt input
  widget mode, which has a very similar functionality (but for sase snippets instead of
  xprompts).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/targeted_mini_xprompt.md`

> # Plan: Targeted mini-xprompt authoring in the ACE prompt stack
> ## Outcome and design contract
> Add a third prompt-bar target state: a **targeted mini-xprompt** is one dedicated
> prompt-input pane that edits exactly one simple xprompt definition. It is deliberately
> different from both existing states:
> - A targeted xprompt continues to bind the entire agent-prompt stack and may represent
>   an xprompt swarm.
> - A targeted snippet continues to bind one auxiliary pane to one snippet trigger.
> - A targeted mini-xprompt binds one auxiliary pane to one simple, non-swarm xprompt. It
>   never becomes an agent segment and is excluded from launch, stash, whole-stack

*See full plan file for details.*

