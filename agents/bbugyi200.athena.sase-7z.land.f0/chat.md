# Chat History - ace-run (sase-7z.land.f0--plan)

- **TIMESTAMP:** 2026-07-20 11:01:39 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-7z.land.f0--plan

**Plan:** /home/bryan/.sase/plans/202607/bead_gated_wait.md


## Prompt

#gh:gh_sase-org__sase
#fork:sase-7z.land Can you now help me ensure that phase agents that depend on other phase agents that wind up creating epic plan files (that are auto-approved, since phase agents include the `%auto` directive in their prompt) wait for epics to complete? I'm not sure if we addressed this edge case or not. If not, use your /sase_plan skill to plan the appropriate changes.
 I think we should be able to solve this by adding a new `bead=<bead_id>` kwarg to the `%wait` directive and having every phase agent depend on both the phase agents and their corresponding beads, right? This way, even after the phase agent another phase agent depends on completes by creating and launching an epic plan,  we would still not start the dependent agent until the phase agents of the sub-agent mark the dependency phase agent's corresponding sase bead as closed. %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/bead_gated_wait.md`

> # Plan: Bead-gated %wait for delegated epic phases
> ## Context
> All references below were verified against the current checkout and the sase-core linked repo (open it with the
> `/sase_repo` skill; per the Rust Core Backend Boundary memory, shared domain behavior belongs there).
> **The gap.** Every epic phase segment rendered by `render_multi_prompt` (`src/sase/bead/work.py:292-379`) carries
> `%auto` (line 352) and waits only on blocker phase _agents_ (`%w:<names>`, line 354); the land segment likewise waits
> only on phase agents (line 375). Medium/large phases also get `#plan` (lines 356-357). When such a phase agent proposes
> an epic-tier plan, `%auto` approves it and `prepare_epic_launch` (`src/sase/_plan_approval_epic.py:16`) spawns the child
> epic as a separate detached clan named after the child epic bead (e.g. phase bead `foo-5.2` begets clan `foo-5.2.1`).
> The proposing phase agent's house then completes, and wait resolution (`src/sase/core/wait_dependency_resolution/`) —

*See full plan file for details.*

