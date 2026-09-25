# Chat History - ace-run (06a--plan)

- **TIMESTAMP:** 2026-08-18 11:25:37 EDT
- **MODEL:** claude/opus
- **AGENT:** 06a--plan

**Plan:** /home/bryan/.sase/plans/202608/flag_task_type.md


## Prompt

#gh:gh_sase-org__sase Can you help me migrate sase flag beads to a new "flag" task bead type (see the
sase-p3 epic bead for context on task bead types)?

- We made a mistake when we initially designed sase flags.
- For one, sase's feature flags are only applicable to the "sase" sase project.
- Also we should only support two kinds of Feature Flags (I think we support 4 ATM):
  - `beta`: for new potentially unstable features
  - `sunset`: for deprecations (so we can remove deprecated features behind a feature
    flag) and/or for backward-compatibilty logic (which should always be removed at some
    point).
- Existing flag beads have terrible descriptions. Make sure this new flag task bead type
  has some useful required fields that agents must set in order to create a new flag.
  Think hard about which fields to require.
- This new flag task bead type should be defined in project-local configuration (e.g. in
  this repo's sase/sase.yml file).
- Make sure to migrate any existing flag beads over to new "flag" task beads.
- Make sure that any memory files related to feature flags/flag beads are
  updated/deleted appropriately.
- See the sase-pq epic bead for related work that is in-progress. Make sure that your
  work does not conflict with that epic (and that the "flag" task type are eventually
  supported on all the same UI surfaces). Leave notes on that epic bead and/or that epic
  bead's phase beads if necessary to coordinate (the epic lander agent will read these
  at the very least, but phase agents will also read their bead notes when they are
  first launched).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/flag_task_type.md`

> # Plan: A feature flag is a task bead, not a bead type
> ## The mistake being corrected
> SASE feature flags were given their own bead **issue type** (`flag`), alongside `plan`,
> `phase`, and `task`. That was wrong in three ways, and this epic fixes all three.
> 1. **A flag is not a fourth kind of thing.** It is a task: "retire this flag." Giving it
>    its own issue type bought a bespoke storage field (`FlagRecord` on the bead wire, a
>    `flag` column in the compatibility mirror, a `flag` block in the update event), a
>    bespoke create grammar (`-T 'flag(<key>,<date>,<release>)'`), a bespoke presentation
>    entry, and a bespoke row kind in the ACE pane — all to express something the
>    task-type system, which did not exist when flags were designed, now expresses

*See full plan file for details.*

