# Chat History - ace-run (0cx--plan)

- **TIMESTAMP:** 2026-08-24 17:21:33 EDT
- **MODEL:** claude/opus
- **AGENT:** 0cx--plan

**Plan:** /home/bryan/.sase/plans/202608/core_memory_priority.md


## Prompt

#gh:gh_sase-org__sase Can you help me add an optional `priority` field to "core" memory files (see
the sase-sq epic bead for context--leave notes on this bead / this bead's children if
appropriate) that specifies the order it is rendered in the "Tier 1" section in agent
instruction files?

- This field should have a default value of `20`.
- We should give the auto-generated (by the `sase init` command) sase/memory/sase.md
  memory file a priority of `10` so it is always the first sub-section of the "Tier 1"
  section (unless a user explicitly sets a lower priority using the `priority`
  frontmatter field in one of their core memory files).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/core_memory_priority.md`

> # Plan: Optional `priority` frontmatter for core memory ordering
> ## Goal
> Today the Tier 1 (core) Memory section of `AGENTS.md` (and every provider shim copied
> from it) renders core notes in **path order**. That is an accident of implementation,
> not a deliberate reading order: `src/sase/amd/_memory.py` builds the inlined bodies with
> `dict(sorted(bodies.items()))`, so `artifact_relations.md` leads and the note that
> actually orients an agent — `sase/memory/sase.md` — lands in the middle.
> This plan adds an optional `priority:` integer to memory-note frontmatter:
> - Default `20` when absent.
> - Lower sorts earlier; ties break on the existing relative-path order, so today's output

*See full plan file for details.*

