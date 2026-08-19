# Chat History - ace-run (07h--plan)

- **TIMESTAMP:** 2026-08-19 07:46:32 EDT
- **MODEL:** claude/opus
- **AGENT:** 07h--plan

**Plan:** /home/bryan/.sase/plans/202608/glossary_tier1_memory_note.md


## Prompt

#gh:gh_sase-org__sase We currently render instructions about the glossary in a Glossary terms subsection of the tier two section in agent instruction files. Can you help me start having the `sase init` command generate a sase/memory/glossary.md short-term memory file instead, which will then be rendered in agent instruction files in the tier 1 section? As a part of this change let's remove the `Long-Term Memory Files` H3 section (put its contents directly in the H2 tier 2 section).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/glossary_tier1_memory_note.md`

> # Plan: Glossary becomes a Tier 1 memory note; Tier 2 loses its H3 wrapper
> ## Goal
> Two structural changes to generated agent instruction files, landed together because
> both rewrite the same `AGENTS.md` render path and both force a regeneration of this
> repo's committed instruction files.
> 1. **Glossary moves to Tier 1 as a real note.** `sase memory init` renders a generated
>    short-term memory note at `sase/memory/glossary.md` from the project's
>    `memory.glossary` config. The existing short-note inlining machinery then renders it
>    into the Tier 1 section of `AGENTS.md` and every provider shim. The Tier 2
>    `Glossary Terms` H3 section is deleted.

*See full plan file for details.*

