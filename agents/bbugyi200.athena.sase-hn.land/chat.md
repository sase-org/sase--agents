# Chat History - ace-run (sase-hn.land--plan)

- **TIMESTAMP:** 2026-08-09 00:10:45 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-hn.land--plan

**Plan:** /home/bryan/.sase/plans/202608/patch_terminology_completion.md


## Prompt

#gh:gh_sase-org__sase
%id(land, clan=sase-hn, bead=sase-hn)
%model:@big_epic_lander
%auto
%w:sase-hn.2,sase-hn.3,sase-hn.4,sase-hn.5,sase-hn.6,sase-hn.7
%w(bead=sase-hn.1)
%w(bead=sase-hn.2)
%w(bead=sase-hn.3)
%w(bead=sase-hn.4)
%w(bead=sase-hn.5)
%w(bead=sase-hn.6)
%w(bead=sase-hn.7)
You are the land agent for epic bead sase-hn: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-hn` (children, linked plan file), review the epic bead's own notes, then
   run `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-hn, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Close the epic with
   `sase bead close sase-hn --note "<what you verified in steps 1-2>"`. AFTER closing, run `just symvision`
   if available (epic-symbol whitelist entries for sase-hn expire at close) and remove the stale entries
   and unused code it reports. Finally, set `status: done` in the frontmatter of the epic's plan file (the PLAN
   path shown by `sase bead show`). If the close is rejected, the named phases were never completed: finish or
   reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make the command succeed.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Make step 3 the plan's final phase (close, run symvision, mark the plan file done)
so the agent that executes the plan finishes the landing. Otherwise do step 3 now.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/patch_terminology_completion.md`

> - **PARENT:**
>   [202608/patch_and_stitch_terminology.md](202608/patch_and_stitch_terminology.md)
> # Finish the Patch/stitch terminology migration and land epic sase-hn
> ## Why this plan exists
> Epic `sase-hn` ("Rename ChangeSpec to Patch and introduce stitches") closed all seven of
> its phases, and its landing verification found the tree green (`just check` passes,
> `just symvision` passes, both discovered issues recorded on the epic bead are genuinely
> fixed). But the epic's own acceptance contract is not met yet, so it cannot be closed as
> done.
> The approved epic plan (`plans:202608/patch_and_stitch_terminology.md`) states:

*See full plan file for details.*

