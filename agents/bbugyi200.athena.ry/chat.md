# Chat History - ace-run (ry--plan)

- **TIMESTAMP:** 2026-08-02 10:03:43 EDT
- **MODEL:** claude/opus
- **AGENT:** ry--plan

**Plan:** /home/bryan/.sase/plans/202608/commit_ref_completion.md


## Prompt

#gh:gh_sase-org__sase Can you help me add improve the `@commit:` artifact reference by giving it excellent argument completion in the prompt input widget and in external editors (via LSP support)? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/commit_ref_completion.md`

> # Plan: Excellent `@commit:` Argument Completion
> ## Goal
> `@commit:<repo>@<sha>` is the only artifact-reference kind whose payload a user must type entirely from memory. This
> plan makes it the easiest one to reach — in the ACE prompt bar and in every LSP editor — without weakening the
> guarantees the other kinds already have.
> Success is three properties, in priority order:
> 1. **Reliable.** Every row the menu offers resolves at launch. Completion never depends on which TUI pane the user has
>    visited, and never contacts the network.
> 2. **Intuitive.** An empty query lists the project's most recent commits, newest first. A query narrows by repo, by SHA
>    prefix, or by subject words, in any combination, without the user having to know which field they are matching.

*See full plan file for details.*

