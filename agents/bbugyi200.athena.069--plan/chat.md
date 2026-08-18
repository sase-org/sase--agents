# Chat History - ace-run (069--plan)

- **TIMESTAMP:** 2026-08-18 10:50:56 EDT
- **MODEL:** claude/opus
- **AGENT:** 069--plan

**Plan:** /home/bryan/.sase/plans/202608/glossary_batched_reads.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support to the `sase glossary show/read` commands for accepting multiple terms as arguments?

- The goal with this change would be to reduce the amount of tokens used by the glossary.
- Make sure the auto-generated glossary section in agent instruction files is updated to recommend reading all terms at once if possible.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/glossary_batched_reads.md`

> # Make Batched Glossary Reads The Taught, Reliable, And Cheap Path
> ## Goal
> Cut the tokens agents spend on the glossary by making one batched read the obvious,
> safe, and lean way to consult it.
> Three things must be true when this lands:
> 1. Every agent instruction file tells agents to pass **all** the terms they need to a
>    single `sase glossary read` invocation.
> 2. A batch that names an unknown term reports **every** unresolved reference in one
>    error, with near-miss candidates for each, so one retry fixes the whole batch.
> 3. The rendered closure contains no invisible padding and no footer line that is not

*See full plan file for details.*

