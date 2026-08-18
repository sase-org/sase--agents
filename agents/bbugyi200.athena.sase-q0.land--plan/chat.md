# Chat History - ace-run (sase-q0.land--plan)

- **TIMESTAMP:** 2026-08-18 17:40:12 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-q0.land--plan

**Plan:** /home/bryan/.sase/plans/202608/gh_plugin_workspace_exclusivity.md


## Prompt

#gh:gh_sase-org__sase
%id(land, clan=sase-q0, bead=sase-q0)
%model:@large
%auto
%w:sase-q0.1,sase-q0.2,sase-q0.3,sase-q0.4
%w(bead=sase-q0.1)
%w(bead=sase-q0.2)
%w(bead=sase-q0.3)
%w(bead=sase-q0.4)
You are the land agent for epic bead sase-q0: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-q0` (children, linked plan file), review the epic bead's own notes, then
   run `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-q0, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Before
   closing, run `sase bead epic-symbols sase-q0`. Every listed `--epic-symbol` entry is keyed to this epic
   or one of its phases and goes stale the instant that bead closes. For each entry, either resolve the symbol
   (wire it up, privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist policy) or,
   only when a still-open later bead still needs the exemption, re-key the Justfile line to that open bead. Do not
   leave that judgment for the next agent. `sase bead close` refuses while any of these entries remain. Close the
   epic with `sase bead close sase-q0 --note "<what you verified in steps 1-2>"`. After closing, run
   `just symvision` if available to confirm the whitelist is clean. Finally, set `status: done` in the frontmatter
   of the epic's plan file (the PLAN path shown by `sase bead show`). If the close is rejected because leftover
   `--epic-symbol` entries remain, finish that cleanup and close again. If the close is rejected because named
   phases were never completed: finish or reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make the command succeed, and
   never use `--force` to advance a successful nested landing.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Plan only the remaining work. Do not include this epic's close, symvision pass,
or plan-file status update as a child phase; the child epic's `parent_bead` link is the handoff that lets its land
agent resume this interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from `sase bead show sase-q0`. If there is
no parent bead, finish normally. If the parent is a phase bead, verify this child plan completed the work required
by that phase, close only that parent phase normally with `sase bead close <parent-bead> --note "<what you
verified>"`, and leave the containing epic to its already-waiting land agent. If the parent is a plan bead, review
the parent's previous landing note, all descendants and notes, linked plan file, and post-child drift; rerun
descendant and linked-plan readiness checks before closing it. When the parent plan is still complete, retire any leftover `--epic-symbol`
entries first (`sase bead epic-symbols <parent-bead>`), close it normally with
`sase bead close <parent-bead> --note "<what you rechecked>"`, confirm with `just
symvision`, mark its linked plan file done, and then repeat through directly parented plan ancestors
while each remains fully complete. Stop at the first incomplete or ambiguous parent, record a note on that parent describing the blocker,
and report it in your final response.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/gh_plugin_workspace_exclusivity.md`

> - **PARENT:** [202608/workspace_exclusivity.md](202608/workspace_exclusivity.md)
> # Plan: Extend the workspace-exclusivity guarantee to the sase-github plugin
> ## Why this exists
> Epic `sase-q0` ("Guarantee one agent per workspace") landed four phases in the `sase`
> repo and in `sase-core`:
> - every RUNNING-field mutation is recorded to a durable ledger with before/after
>   occupancy and a caller tag (`src/sase/logs/workspace_claim_ledger.py`);
> - deferred allocation claims atomically **before** materializing a checkout, and a
>   pinned family-attach target is a single-shot checked claim
>   (`src/sase/axe/run_agent_phases.py`);

*See full plan file for details.*

