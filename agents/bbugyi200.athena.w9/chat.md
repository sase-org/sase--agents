# Chat History - ace-run (w9--plan)

- **TIMESTAMP:** 2026-08-09 07:49:36 EDT
- **MODEL:** claude/opus
- **AGENT:** w9--plan

**Plan:** /home/bryan/.sase/plans/202608/glossary_term_underline.md


## Prompt

#gh:gh_sase-org__sase We currently highlight glossary aliases in the prompt input widget and in external editors via LSP support. Can you help me start underlining these terms as well? See how we do this for known misspelled words in the prompt input widget for inspiration. I want you to lead the design on this one. Just make sure it looks beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/glossary_term_underline.md`

> # Plan: Underline glossary terms in ACE prompts and in LSP-backed editors
> ## Why
> A glossary match is the one span in a prompt that has a definition behind it: `K`
> previews it and `Ctrl+]` jumps to its `sase/sase.yml` entry. Today it renders as bold
> theme-accent text, which reads as emphasis rather than as something you can follow.
> Underlining it completes the link idiom, and it binds multiword phrases (`Agent Clan`,
> `agent instruction file`) into one visual unit that bold alone cannot express.
> Both surfaces that highlight glossary matches are in scope, so the affordance does not
> change when a prompt moves from the ACE prompt bar into `$EDITOR`:
> - ACE prompt input: `src/sase/ace/tui/widgets/_prompt_glossary.py`, style

*See full plan file for details.*

