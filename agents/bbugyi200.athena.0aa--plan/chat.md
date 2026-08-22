# Chat History - ace-run (0aa--plan)

- **TIMESTAMP:** 2026-08-22 10:43:15 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0aa--plan

**Plan:** /home/bryan/.sase/plans/202608/restore_final_directive_visibility.md


## Prompt

#gh:gh_sase-org__sase The `%final` directive still isn't shown when I type `%` in the prompt input
widget or in external editors (via LSP support). See the sase-s0 epic bead for context.
Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/restore_final_directive_visibility.md`

> # Restore public `%final` directive completion
> ## Context and root cause
> Epic `sase-s0` completed the configured finalizer catalog, selector-aware value
> completion, ACE presentation, LSP rendering, documentation, and public name exposure.
> Its later parity tale also added positive ACE/LSP assertions for `%final` names and LSP
> snippets. A concurrent integrity-acceptance stitch then restored the old hidden policy:
> - `sase-core` commit `f7e8247` changed
>   `crates/sase_core/src/editor/directive.rs::HIDDEN_COMPLETION_DIRECTIVES` from empty to
>   `['final']`.
> - Main-repository commit `47830f9` changed the focused ACE unit tests back to expecting

*See full plan file for details.*

