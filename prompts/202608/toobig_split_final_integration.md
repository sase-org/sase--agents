- **PLAN:**
  [202608/toobig_split_final_integration.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_final_integration.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-so.land--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-so.land.md)

You are the land agent for epic bead sase-so: verify the epic is truly complete,
integrate it with changes that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-so` (children, linked plan file), review the epic
   bead's own notes, then run `sase bead show` on every child and review every child
   note. Confirm each note was addressed, and read the actual source code and the epic's
   commits (bead IDs appear in commit messages) to confirm the work previous agents
   reported complete really is. While reviewing child beads, collect every
   `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this
   epic's feature while it was incomplete. Find them (e.g. `git log` since the first
   commit mentioning sase-so, excluding the epic's own commits; in a PR workflow also
   review commits on the base branch) and update anything that should now use what this
   epic added or that duplicates or conflicts with it. This integration is part of the
   epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them
   before closing. For each genuinely distinct follow-up that is not caused by the epic,
   use `/sase_new_task` with details identifying the proposing bead; it will corroborate
   a duplicate, attach a causally related active-epic issue, or create a sized task as
   appropriate. Record every outcome, including why any proposal was declined, in your
   close note. Before closing, run `sase bead epic-symbols sase-so`. Every listed
   `--epic-symbol` entry is keyed to this epic or one of its phases and goes stale the
   instant that bead closes. For each entry, either resolve the symbol (wire it up,
   privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist
   policy) or, only when a still-open later bead still needs the exemption, re-key the
   Justfile line to that open bead. Do not leave that judgment for the next agent.
   `sase bead close` refuses while any of these entries remain. Close the epic with
   `sase bead close sase-so --note "<what you verified in steps 1-2>"`. After closing,
   run `just symvision` if available to confirm the whitelist is clean. Finally, set
   `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by
   `sase bead show`). If the close is rejected because leftover `--epic-symbol` entries
   remain, finish that cleanup and close again. If the close is rejected because named
   phases were never completed: finish or reopen them, or record the outcome
   deliberately with `--force --reason ... --resolution canceled|superseded`. Never
   force merely to make the command succeed, and never use `--force` to advance a
   successful nested landing.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete
the skill's tier-aware validate/revalidate/propose loop. Plan only the remaining work.
Do not include this epic's close, symvision pass, or plan-file status update as a child
phase; the child epic's `parent_bead` link is the handoff that lets its land agent
resume this interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from
`sase bead show sase-so`. If there is no parent bead, finish normally. If the parent is
a phase bead, verify this child plan completed the work required by that phase, close
only that parent phase normally with
`sase bead close <parent-bead> --note "<what you verified>"`, and leave the containing
epic to its already-waiting land agent. If the parent is a plan bead, review the
parent's previous landing note, all descendants and notes, linked plan file, and
post-child drift; rerun descendant and linked-plan readiness checks before closing it.
When the parent plan is still complete, retire any leftover `--epic-symbol` entries
first (`sase bead epic-symbols <parent-bead>`), close it normally with
`sase bead close <parent-bead> --note "<what you rechecked>"`, confirm with
`just symvision`, mark its linked plan file done, and then repeat through directly
parented plan ancestors while each remains fully complete. Stop at the first incomplete
or ambiguous parent, record a note on that parent describing the blocker, and report it
in your final response.
