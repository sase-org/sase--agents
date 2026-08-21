# Chat History - ace-run (sase-rr.land.w1--plan)

- **TIMESTAMP:** 2026-08-21 20:34:37 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-rr.land.w1--plan

**Plan:** /home/bryan/.sase/plans/202608/final_directive_completion.md


## Prompt

#gh:gh_sase-org__sase
%w:sase-rr.land Can you help me add good completion for the `%final` directive in the prompt input widget and in external editors (via LSP support)? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/final_directive_completion.md`

> # Plan: Beautiful and reliable `%final` directive completion
> ## Outcome
> Typing `%` in the ACE prompt input or requesting completion in an LSP-enabled external
> editor will advertise `%final` alongside the other public directives. After `%final:` or
> inside `%final(...)`, completion will describe and insert the effective configured
> finalizer instances, support both add and remove selector forms, and offer `none` only
> when clearing the selection is valid.
> The implementation will use one Rust-owned completion contract for filtering,
> replacement, ordering, and LSP behavior. Python will remain the host authority for
> merged finalizer configuration and will expose a small read-only catalog used by ACE

*See full plan file for details.*

