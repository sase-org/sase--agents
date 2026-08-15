- **PLAN:**
  [202608/preserve_models_selection_during_provider_snapshot.md](https://github.com/sase-org/sase--plans/blob/main/202608/preserve_models_selection_during_provider_snapshot.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-mc.5.land--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mc.5.land.md)

You are the land agent for epic bead sase-mc.5: verify the epic is truly complete,
integrate it with changes that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-mc.5` (children, linked plan file), review the epic
   bead's own notes, then run `sase bead show` on every child and review every child
   note. Confirm each note was addressed, and read the actual source code and the epic's
   commits (bead IDs appear in commit messages) to confirm the work previous agents
   reported complete really is. While reviewing child beads, collect every
   `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this
   epic's feature while it was incomplete. Find them (e.g. `git log` since the first
   commit mentioning sase-mc.5, excluding the epic's own commits; in a PR workflow also
   review commits on the base branch) and update anything that should now use what this
   epic added or that duplicates or conflicts with it. This integration is part of the
   epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them
   before closing. For each genuinely distinct follow-up that is not caused by the epic,
   use `/sase_new_task` with details identifying the proposing bead; it will corroborate
   a duplicate, attach a causally related active-epic issue, or create a sized task as
   appropriate. Record every outcome, including why any proposal was declined, in your
   close note. Close the epic with
   `sase bead close sase-mc.5 --note "<what you verified in steps 1-2>"`. AFTER closing,
   run `just symvision` if available (epic-symbol whitelist entries for sase-mc.5 expire
   at close) and remove the stale entries and unused code it reports. Finally, set
   `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by
   `sase bead show`). If the close is rejected, the named phases were never completed:
   finish or reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make
   the command succeed, and never use `--force` to advance a successful nested landing.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete
the skill's tier-aware validate/revalidate/propose loop. Plan only the remaining work.
Do not include this epic's close, symvision pass, or plan-file status update as a child
phase; the child epic's `parent_bead` link is the handoff that lets its land agent
resume this interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from
`sase bead show sase-mc.5`. If there is no parent bead, finish normally. If the parent
is a phase bead, verify this child plan completed the work required by that phase, close
only that parent phase normally with
`sase bead close <parent-bead> --note "<what you verified>"`, and leave the containing
epic to its already-waiting land agent. If the parent is a plan bead, review the
parent's previous landing note, all descendants and notes, linked plan file, and
post-child drift; rerun descendant and linked-plan readiness checks before closing it.
When the parent plan is still complete, close it normally with
`sase bead close <parent-bead> --note "<what you rechecked>"`, run its post-close
symvision cleanup, mark its linked plan file done, and then repeat through directly
parented plan ancestors while each remains fully complete. Stop at the first incomplete
or ambiguous parent, record a note on that parent describing the blocker, and report it
in your final response.
