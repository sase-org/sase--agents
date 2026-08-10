- **PLAN:**
  [202608/tale_size_plan_lane.md](https://github.com/sase-org/sase--plans/blob/main/202608/tale_size_plan_lane.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-il.land.f1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-il.land.f1.md)

%xprompts_enabled:false

# Previous Conversation

**User:**

You are the land agent for epic bead sase-il: verify the epic is truly complete,
integrate it with changes that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-il` (children, linked plan file), review the epic
   bead's own notes, then run `sase bead show` on every child and review every child
   note. Confirm each note was addressed, and read the actual source code and the epic's
   commits (bead IDs appear in commit messages) to confirm the work previous agents
   reported complete really is. While reviewing child beads, collect every
   `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this
   epic's feature while it was incomplete. Find them (e.g. `git log` since the first
   commit mentioning sase-il, excluding the epic's own commits; in a PR workflow also
   review commits on the base branch) and update anything that should now use what this
   epic added or that duplicates or conflicts with it. This integration is part of the
   epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them
   before closing. For each genuinely distinct follow-up that is not caused by the epic,
   use `/sase_new_task` with details identifying the proposing bead; it will corroborate
   a duplicate, attach a causally related active-epic issue, or create a sized task as
   appropriate. Record every outcome, including why any proposal was declined, in your
   close note. Close the epic with
   `sase bead close sase-il --note "<what you verified in steps 1-2>"`. AFTER closing,
   run `just symvision` if available (epic-symbol whitelist entries for sase-il expire
   at close) and remove the stale entries and unused code it reports. Finally, set
   `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by
   `sase bead show`). If the close is rejected, the named phases were never completed:
   finish or reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make
   the command succeed.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete
the skill's tier-aware validate/revalidate/propose loop. Make step 3 the plan's final
phase (close, run symvision, mark the plan file done) so the agent that executes the
plan finishes the landing. Otherwise do step 3 now.

**Assistant:**

_Plan submitted for review._

**Plan file:** `/home/bryan/.sase/plans/202608/finish_tale_size_semantics.md`

> - **PARENT:** [202608/sase_sizes_memory.md](202608/sase_sizes_memory.md)
>
> # Plan: Finish core-owned tale size semantics and land sase-il
>
> Epic `sase-il` made one generated memory note (`sase/memory/sase_sizes.md`) the
> canonical source of sase-size truth, gave tale plans a required `size`, and retired
> the coder alias bucket. Landing verification confirmed five of six phases are complete
> and correct. Phase `sase-il.3` (`core-tale-size`), however, shipped a partial contract
> in `sase-core`, and `sase-il.4` recorded the gap as a `PROPOSED FOLLOW-UP` rather than
> closing it. Because the epic's own memory note and `/sase_plan` skill already publish
> the stricter rule, the repo currently documents one contract and enforces another.
> Three concrete gaps remain, all in
> `../sase-core/crates/sase_core/src/plan/validate.rs`

_See full plan file for details._

---

%xprompts_enabled:true

# New Query

Can you help me make sure that a tale plan's size has appropriate representation in the
`PLAN` lane of the `SASE CONTEXT` section in the agent metadata panel? If not, use your
/sase_plan skill to plan the appropriate changes.
