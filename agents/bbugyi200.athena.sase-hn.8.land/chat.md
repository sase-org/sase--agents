# Chat History - ace-run (sase-hn.8.land--plan)

- **TIMESTAMP:** 2026-08-09 04:14:46 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-hn.8.land--plan

**Plan:** /home/bryan/.sase/plans/202608/patch_audit_gate_repair.md


## Prompt

#gh:gh_sase-org__sase
%id(land, clan=sase-hn.8, bead=sase-hn.8)
%model:@big_epic_lander
%auto
%w:sase-hn.8.1,sase-hn.8.2,sase-hn.8.3,sase-hn.8.4,sase-hn.8.5
%w(bead=sase-hn.8.1)
%w(bead=sase-hn.8.2)
%w(bead=sase-hn.8.3)
%w(bead=sase-hn.8.4)
%w(bead=sase-hn.8.5)
You are the land agent for epic bead sase-hn.8: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-hn.8` (children, linked plan file), review the epic bead's own notes, then
   run `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-hn.8, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Close the epic with
   `sase bead close sase-hn.8 --note "<what you verified in steps 1-2>"`. AFTER closing, run `just symvision`
   if available (epic-symbol whitelist entries for sase-hn.8 expire at close) and remove the stale entries
   and unused code it reports. Finally, set `status: done` in the frontmatter of the epic's plan file (the PLAN
   path shown by `sase bead show`). If the close is rejected, the named phases were never completed: finish or
   reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make the command succeed.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Make step 3 the plan's final phase (close, run symvision, mark the plan file done)
so the agent that executes the plan finishes the landing. Otherwise do step 3 now.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/patch_audit_gate_repair.md`

> - **PARENT:**
>   [202608/patch_terminology_completion.md](202608/patch_terminology_completion.md)
> # Repair the Patch/stitch terminology gate and finish the test-tree sweep
> ## Why this plan exists
> Epic `sase-hn.8` ("Finish the Patch/stitch terminology migration and land epic
> `sase-hn`") closed all five of its phases, but its landing verification found two
> defects that the epic itself introduced. Both are in the final phase's commit
> `cac21c867` ("fix: enforce Patch terminology audit gate", `sase-hn.8.5`). The epic
> cannot be closed until they are resolved, because unresolved issues caused by an epic
> remain that epic's work.

*See full plan file for details.*

