# Chat History - ace-run (sase-5h.w1--plan)

- **TIMESTAMP:** 2026-07-07 15:35:45 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-5h.w1--plan

**Plan:** /home/bryan/.sase/plans/202607/vcs_ref_colon_completion.md


## Prompt

#gh:gh_sase-org__sase %w:sase-5h We recently added support for `/` completion for the `#gh` VCS xprompt workflow (see the sase-5h epic bead). Can you now help me add support for another type of VCS xprompt workflow completion?

- Namely, I want to start triggering completion for all known `#gh` / `#git` project/ChangeSpec names when the `:` key is pressed.
- For VCS types that support organizations (like `#gh`), we should also show any organizations that correspond with existing, active sase projects. For example, on this machine we should always show the `bbugyi200` and `sase-org` GitHub organizations when the user types `#gh:`.
- Make sure it is clear which entries in the completion menu are projects vs ChangeSpecs vs organizations.
- We should trigger this type of completion from the prompt input widget and the user's editor via LSP support.
- We already have logic that loads the correct completion sources. See the TUI's `+` keymap for context.
- For example, if the user types `#git:` in the prompt input widget, they should trigger a completion menu for all known bare-git projects/ChangeSpecs.
- Make sure we add support in a VCS-agnostic (remember that new VCS system support is likely to be added via a sase plugin repo that we might never have access to) way so future VCS systems get support automatically or at the very least easily. 
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/vcs_ref_colon_completion.md`

> # Plan: VCS-Agnostic Ref Completion for `#gh:` / `#git:` (the `:` trigger)
> ## Problem & Product Context
> The `sase-5h` epic taught sase to complete the _second_ half of a VCS ref: typing `/` inside `#gh:bbugyi200/` opens a
> live repo menu. But the _first_ half is still a memory test. Typing `#gh:` or `#git:` today shows only the
> candidate-less xprompt argument hint — the user must remember project names, active ChangeSpec names, and GitHub owner
> spellings unaided, even though sase already knows all three. We even solved this exact problem _cross-provider_ with the
> `#+` menu (epic `sase-4z`); this plan brings the same data to the provider-scoped moment where the user has already
> committed to a VCS type: **when the user types `:` (or `(`) after a VCS workflow tag, open a completion menu listing
> every ref that tag can accept** — active projects, active ChangeSpecs, and (for providers that have them) organizations
> — in both frontends:

*See full plan file for details.*

