# Chat History - ace-run (08s--plan)

- **TIMESTAMP:** 2026-08-20 13:43:47 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 08s--plan

**Plan:** /home/bryan/.sase/plans/202608/xprompt_directive_completion_parity.md


## Prompt

#gh:gh_sase-org__sase Can you help me make sure that every single xprompt directive and every single xprompt directive keyword argument has excellent completion support in the prompt input widget and external editors (via LSP support)? If not, use your /sase_plan skill to plan the appropriate changes.
 For example, doesn't the `%wait` directive have a `bead=` keyword argument (see #sshot for context)?

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/xprompt_directive_completion_parity.md`

> # Complete xprompt directive completion in ACE and external editors
> ## Outcome
> Make directive assistance complete and trustworthy in both editing surfaces. A user who
> types a directive name, an allowed syntax delimiter, a keyword fragment, or a value for
> a structured keyword should see the same valid, well-described choices in ACE's prompt
> input and in an LSP client. Completion must never advertise syntax the runtime
> interprets differently, and adding a runtime directive or keyword must fail a parity
> test until the shared completion contract is updated.
> This is an epic because the canonical editor/domain behavior belongs in `sase-core`,
> while the xprompt LSP and ACE prompt widget need separate integrations and dynamic

*See full plan file for details.*

