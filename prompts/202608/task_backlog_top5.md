- **PLAN:**
  [202608/task_backlog_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-ns.land--1--plan](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.land--1--plan/README.md)

%xprompts_enabled:false

# Previous Conversation

**User:**

You are the land agent for epic bead sase-ns: verify the epic is truly complete,
integrate it with changes that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-ns` (children, linked plan file), review the epic
   bead's own notes, then run `sase bead show` on every child and review every child
   note. Confirm each note was addressed, and read the actual source code and the epic's
   commits (bead IDs appear in commit messages) to confirm the work previous agents
   reported complete really is. While reviewing child beads, collect every
   `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this
   epic's feature while it was incomplete. Find them (e.g. `git log` since the first
   commit mentioning sase-ns, excluding the epic's own commits; in a PR workflow also
   review commits on the base branch) and update anything that should now use what this
   epic added or that duplicates or conflicts with it. This integration is part of the
   epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them
   before closing. For each genuinely distinct follow-up that is not caused by the epic,
   use `/sase_new_task` with details identifying the proposing bead; it will corroborate
   a duplicate, attach a causally related active-epic issue, or create a sized task as
   appropriate. Record every outcome, including why any proposal was declined, in your
   close note. Close the epic with
   `sase bead close sase-ns --note "<what you verified in steps 1-2>"`. AFTER closing,
   run `just symvision` if available (epic-symbol whitelist entries for sase-ns expire
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
`sase bead show sase-ns`. If there is no parent bead, finish normally. If the parent is
a phase bead, verify this child plan completed the work required by that phase, close
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

**Assistant:**

# Monitor handoff

This agent delegated the remaining work to a monitor shell. Monitor ID: v3c1d2dezr82
Inspect with: sase monitor show v3c1d2dezr82 Monitor shell: sase-ns.land--mon Directory:
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14

Command:

```sh
sleep 1
```

Reason:

Hand the remaining sase task-bead backlog to a fresh agent shell

Next action:

Complete the work recommended by previous agents by following these steps: (1) Review
all of my current open (not in-progress) sase task beads for the "sase" sase project.
(2) Close any task beads that are no longer relevant with a good reason. (3) Select the
5 task beads that would have the most impact if worked to completion. (4) Use your
/sase_plan skill to fix the issues / make the improvements that correspond with these 5
task beads. Make sure the plan file you propose tells the agent(s) to: (a) if you think
any of these 5 beads need approval from the user before working (be lenient here and do
not ask for approval for objective improvements), do not ask directly, but instead leave
a `TASK NEEDS APPROVAL` note on the bead; (b) mark the bead(s) you intend to work as
in-progress by changing their status with the `sase bead update` command; (c) leave a
brief note on the task bead(s) explaining the work that was done to fix the reported
issue / make the requested improvement or, if the agent was unable to complete the work,
justifying why they were unable to do so; (d) close each of the 5 task beads that it was
able to finish; (e) if there are more task beads associated with the "sase" project, the
agent should then start a pseudo monitor using the `sleep 1` command with a next action
that instructs the next agent to follow this exact prompt (with these exact same steps);
(f) if there are no more task beads to work, the agent should move on to the next
numbered step in this prompt. (5) Review all `TASK NEEDS APPROVAL` notes left by prior
agent shells and consolidate them into a single report for the user with suggested next
actions. (6) Terminate.

---

%xprompts_enabled:true

# New Query

%xprompts_enabled:false

# Monitored command finished

**Command:**

```text
sleep 1
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
```

|              |                                                                  |
| ------------ | ---------------------------------------------------------------- |
| **Outcome**  | COMPLETED — exit 0                                               |
| **Started**  | 2026-08-17T00:00:46.147934+00:00                                 |
| **Finished** | 2026-08-17T00:00:48.209409+00:00                                 |
| **Elapsed**  | 1s of a 5m 0s budget                                             |
| **Output**   | 0 bytes · full log: `sase monitor show v3c1d2dezr82 --all-lines` |

**Why this was monitored:** Hand the remaining sase task-bead backlog to a fresh agent
shell

## Your next action

Complete the work recommended by previous agents by following these steps: (1) Review
all of my current open (not in-progress) sase task beads for the "sase" sase project.
(2) Close any task beads that are no longer relevant with a good reason. (3) Select the
5 task beads that would have the most impact if worked to completion. (4) Use your
/sase_plan skill to fix the issues / make the improvements that correspond with these 5
task beads. Make sure the plan file you propose tells the agent(s) to: (a) if you think
any of these 5 beads need approval from the user before working (be lenient here and do
not ask for approval for objective improvements), do not ask directly, but instead leave
a `TASK NEEDS APPROVAL` note on the bead; (b) mark the bead(s) you intend to work as
in-progress by changing their status with the `sase bead update` command; (c) leave a
brief note on the task bead(s) explaining the work that was done to fix the reported
issue / make the requested improvement or, if the agent was unable to complete the work,
justifying why they were unable to do so; (d) close each of the 5 task beads that it was
able to finish; (e) if there are more task beads associated with the "sase" project, the
agent should then start a pseudo monitor using the `sleep 1` command with a next action
that instructs the next agent to follow this exact prompt (with these exact same steps);
(f) if there are no more task beads to work, the agent should move on to the next
numbered step in this prompt. (5) Review all `TASK NEEDS APPROVAL` notes left by prior
agent shells and consolidate them into a single report for the user with suggested next
actions. (6) Terminate. %xprompts_enabled:true
