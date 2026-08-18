# Chat History - ace-run (sase-ng.1.land--plan)

- **TIMESTAMP:** 2026-08-17 19:02:20 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ng.1.land--plan

## Prompt

#gh:gh_sase-org__sase
%id(land, clan=sase-ng.1, bead=sase-ng.1)
%model:@xlarge
%auto
%w:sase-ng.1.1,sase-ng.1.2,sase-ng.1.3,sase-ng.1.4,sase-ng.1.5,sase-ng.1.6
%w(bead=sase-ng.1.1)
%w(bead=sase-ng.1.2)
%w(bead=sase-ng.1.3)
%w(bead=sase-ng.1.4)
%w(bead=sase-ng.1.5)
%w(bead=sase-ng.1.6)
You are the land agent for epic bead sase-ng.1: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-ng.1` (children, linked plan file), review the epic bead's own notes, then
   run `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-ng.1, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Before
   closing, run `sase bead epic-symbols sase-ng.1`. Every listed `--epic-symbol` entry is keyed to this epic
   or one of its phases and goes stale the instant that bead closes. For each entry, either resolve the symbol
   (wire it up, privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist policy) or,
   only when a still-open later bead still needs the exemption, re-key the Justfile line to that open bead. Do not
   leave that judgment for the next agent. `sase bead close` refuses while any of these entries remain. Close the
   epic with `sase bead close sase-ng.1 --note "<what you verified in steps 1-2>"`. After closing, run
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

After the current epic closes, inspect the linked `parent_bead` from `sase bead show sase-ng.1`. If there is
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

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: 7jzhrte86141
Inspect with: sase monitor show 7jzhrte86141
Monitor shell: sase-ng.1.land--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13

Command:

```sh
just check-full
```

Reason:

Combined-tree gate the sase-ng.1 epic plan requires before landing; lint and targeted suites already green at HEAD c89e5bbeb

Next action:

You are resuming the landing of epic bead sase-ng.1 (Retire dead ACE in-process launch and cleanup bodies). Steps 1 and 2 of the landing are already DONE and recorded in full as the "LANDING VERIFICATION (sase-ng.1.land, HEAD c89e5bbeb)" note on sase-ng.1; read it with `sase bead show sase-ng.1` before acting. Do not redo that verification. The only thing that was outstanding is the combined-tree `just check-full` gate the epic plan requires before the close, which is the run you are being handed.

TRIAGE THE RESULT FIRST.
- Two gates are known-red on master and are NOT this epic's work. Do not file new task beads for them. tools/check_test_cost_budgets (peak_worker_rss_kib, causes.ace_page_enter, causes.parser_create, causes.textual_app_run_test_enter) is tracked on sase-j0 - phases sase-ng.1.5 and sase-ng.1.6 already recorded +1s there, so this reporter has already counted; add `sase bead note sase-j0` with this run's numbers instead of another +1. `just selection-health --fail-on-new-flake` overflow nodes are tracked on sase-jq, sase-jb, sase-kd and peers - triage each named node through your sase_new_task skill and corroborate rather than creating duplicates.
- Any lint/fmt/mypy/symvision failure, or any pytest failure, is a real blocker. Reproduce it, then decide whether this epic caused it by stashing or by checking whether the failing area touches the epic's surface (durable RUN_LAUNCH payloads, sase.agent.force_reuse_launch, src/sase/main/query_handler/_launch.py, ACE launch/cleanup proc submission, ops/commands/agent.py cleanup payload application). If this epic caused it, that is remaining epic work: use your sase_plan skill to plan just the remaining work and complete its validate/revalidate/propose loop, and do NOT close. If it is unrelated and pre-existing, record it per the bead policy and continue to the close.

IF THE RUN IS CLEAN (or fails only on the two known-red gates above), FINISH THE LANDING IN THIS ORDER.
1. `sase bead epic-symbols sase-ng.1` must still report no entries (it did at handoff, and the Justfile whitelist holds only sase-n4.5/sase-n4/sase-p1.2 lines).
2. Close the epic: `sase bead close sase-ng.1 --note "<note>"`. The note must state what was verified in landing steps 1 and 2 - summarize the LANDING VERIFICATION note on the bead (deleted module inventory confirmed absent, zero proc_callable in src with only the preserved _submit_session_worker seam left in tests, force-reuse/warning-toast/cleanup-recovery wiring confirmed end to end, all child PROPOSED FOLLOW-UPs resolved with sase-p6 and sase-p7 filed ready and the sase-oc/sase-j0/force-reuse-assertion proposals resolved without new beads, the epic's own DISCOVERED ISSUE note confirmed stale because 65b72d43a already removed all six sase-ng.1.5 entries, and the nine non-epic commits since 97f5b6f03 reviewed with Justfile-only overlap and no doc or code owed) - and add this check-full run's outcome.
3. `just symvision` to confirm the whitelist is clean.
4. Set `status: done` in the frontmatter of /home/bryan/.sase/plans/202608/retire_dead_ace_launch_cleanup_bodies.md (the epic's PLAN path).
5. PARENT HANDLING. sase-ng.1's parent is sase-ng, which is a TASK bead (not a phase and not a plan bead), currently in_progress, sized large, and its description asks for exactly the work this epic delivered: retire both dead in-process body families and both proc_callable parameters and migrate the affected test doubles onto the durable submit paths. Confirm that against the closed epic, then close it normally with `sase bead close sase-ng --note "<what you verified>"`, noting that sase-p6 and sase-p7 carry the two capabilities the plan deliberately scoped out. sase-ng has no parent above it, so stop there. If anything about sase-ng looks incomplete or ambiguous, do not force it: leave it open, put a note on it describing the blocker, and say so in your final response.

Never use --force on any close here. Report the check-full outcome, the closes you made, and anything you left open.

