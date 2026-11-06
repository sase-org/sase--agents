# Chat History - ace-run (sase-1qz.6.1.land--plan)

- **TIMESTAMP:** 2026-11-06 11:33:32 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1qz.6.1.land--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1qz_6_1_land__plan-261104_150254.md`
- 2. --code — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1qz_6_1_land__code-261104_150254.md`

**Plan:** /home/bryan/.sase/plans/202611/hijack_recovery_settlement_completion.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/hijack_recovery_settlement_completion.md`

> - **PARENT:** [202611/hijack_keep_work_recovery.md](202611/hijack_keep_work_recovery.md)
> - **BEAD:** sase-1qz.6.1
> # Plan: Finish hijack recovery settlement and close the keep-work epic
> ## Context
> This tale is the landing remainder of epic **sase-1qz.6.1** ("Complete keep-work
> recovery for hijacked agents"). Its authoritative contract is
> `plan:202611/hijack_keep_work_recovery.md`; read it with
> `sase artifact read plan:202611/hijack_keep_work_recovery.md "<why>"`. In particular,
> read the "Invariants and shared interfaces" list and the `reconcile_wait` phase. Also
> run `sase bead read sase-1qz.6.1 -r "<why>"` and read the land notes at the end. They

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(land, clan=sase-1qz.6.1, bead=sase-1qz.6.1)
%model:@xlarge
%w(sase-1qz.6.1.2,sase-1qz.6.1.4,sase-1qz.6.1.5,sase-1qz.6.1.6,sase-1qz.6.1.7, for_epic=false)
%w(bead=sase-1qz.6.1.1)
%w(bead=sase-1qz.6.1.2)
%w(bead=sase-1qz.6.1.3)
%w(bead=sase-1qz.6.1.4)
%w(bead=sase-1qz.6.1.5)
%w(bead=sase-1qz.6.1.6)
%w(bead=sase-1qz.6.1.7)
You are the land agent for epic bead sase-1qz.6.1: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

Do not run `just check-full` unless this prompt or the user explicitly tells you to. File-change verification is
`just check`. A `just check` pass with a `just check-full` failure is a test-infrastructure bug, not remaining
epic work.

1. Verify. Run `sase bead read sase-1qz.6.1 -r "Need the epic scope, children, and linked plan file"`, review the epic bead's own notes, then
   run `sase bead read <child-id> -r "Need the child scope and notes"` on every child and review every child note. Confirm each note was addressed, and confirm the work honored the epic's DECISIONS, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-1qz.6.1, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Before
   closing, run `sase bead epic-symbols sase-1qz.6.1`. Every listed `--epic-symbol` entry is keyed to this epic
   or one of its phases and goes stale the instant that bead closes. For each entry, either resolve the symbol
   (wire it up, privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist policy) or,
   only when a still-open later bead still needs the exemption, re-key the Justfile line to that open bead. Do not
   leave that judgment for the next agent. `sase bead close` refuses while any of these entries remain. Close the
   epic with `sase bead close sase-1qz.6.1 --note "<what you verified in steps 1-2>"`. After closing, run
   `just symvision` if available to confirm the whitelist is clean. Finally, set `status: done` in the frontmatter
   of the epic's plan file (the PLAN path shown by `sase bead read`). If the close is rejected because leftover
   `--epic-symbol` entries remain, finish that cleanup and close again. If the close is rejected because named
   phases were never completed: finish or reopen them, or record the outcome deliberately with
   `--force --reason ... --resolution canceled|superseded`. Never force merely to make the command succeed, and
   never use `--force` to advance a successful nested landing.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Plan only the remaining work. Prefer `tier: tale`: choose a tale whenever one
coding agent can finish the remaining work directly (`xsmall`, `small`, or `medium` per the SASE size guidance).
Author a child `epic` only when the remaining work genuinely needs multiple agents or phases, or is too large
(`large`/`xlarge`) for one agent to implement directly. A tale has no land agent of its own and nothing resumes
this landing after its coder finishes, so a lander-authored tale must finish the landing itself. The tale's
closeout must never wait for, or be ordered after, a step that needs this work's own commit (its SHA, push, or
CI result): closing the epic in the same turn as the final code is the normal landing. After proposing, finish
through `/sase_final` so this lander's integration edits commit before the host adopts the proposal. Before
proposing the tale, finish the step-3 follow-up triage yourself: for each genuinely distinct follow-up that is not caused by
the epic, use `/sase_new_task` with details identifying the proposing bead, and record every outcome, including why
any proposal was declined, with `sase bead note sase-1qz.6.1 "..."`. The tale's final step must be this epic's
closeout, written concretely so the coder needs no other context: resolve or re-key every
`sase bead epic-symbols sase-1qz.6.1` entry, then close the epic with
`sase bead close sase-1qz.6.1 --note "<verification>"`, run `just symvision`, and set `status: done` in the
epic's plan file (the PLAN path shown by `sase bead read`); when the epic has a `parent_bead`, handle that parent
as described in the final paragraph below, using the concrete parent ID. The step-3 rules still apply in the tale:
never use `--force` merely to make the close succeed, and never use `--force` to advance a successful nested
landing. For the child-epic path: Do not include this epic's close, symvision pass, or plan-file status update
as a child phase; the child epic's `parent_bead` link is the handoff that lets its land agent resume this
interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from `sase bead read sase-1qz.6.1 -r "Need the parent link"`. If there is
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

Reviewed all seven child phases (all closed); now checking the parent phase sase-1qz.6, the epic's commits, and source.

Checking the recovery CLI, the core pin, and the symbols that were re-keyed to sase-1qz.7.

I'll delegate an independent source audit of the later phases while I run the focused test suite and review the integration commits myself.

290 focused tests pass, but the auditor reported three blocking gaps in crash reconciliation. Verifying those claims directly in the source before acting on them.

Checking whether anything else drives reconciliation once the successor owns the claim.

Confirmed gap 2 (no pending-repair registration before the settle CAS). Now checking gap 3 against the Rust decision and the Python observer.

Gap 3 confirmed in Rust: `begin_resolution` always records launch evidence, so an "absent" observation can never return to held. Checking whether the queued dispatch path settles anywhere.

Gaps 1–3 are confirmed. Checking the expired-hijack wait claim (gap 4), since the plan explicitly requires expired hijacks to stay parked.

Reviewer gaps 1–3 are real and block completion; I'll fold gap 4 and the test gaps into the remaining-work plan. Now doing the step-2 integration review of the non-epic commits.

Sweep found no task for the `monkeypatch.undo()` isolation-guard offender; checking it still reproduces and who introduced it before filing.

The offender was introduced by `45bcf6fe39` under phase sase-1ra.5. Checking whether epic sase-1ra is still active (causal-link branch) and reviewing in-progress epics.

sase-r2 (same pipe e2e node, same full-lane-only symptom) is the duplicate. Checking the remaining flake beads (sase-1al, sase-1mr, sase-1oy, sase-1ew) before corroborating.

Same abandoned-`index.lock` recovery mechanism as sase-1kr, so that is the duplicate. Recording the corroborations now.

Follow-up triage is done. Recording the outcomes and the verification findings on the epic, then planning the remaining work.

Plan written; validating it.

I haven't closed epic sase-1qz.6.1. Checking the code turned up three gaps that block it, so I've proposed a follow-up plan to fix them and then close the epic. That plan starts after this turn ends. This turn changed no code, so there is nothing to commit.

**What checked out:**
- All seven phases are closed and their notes were addressed.
- The 290 focused recovery tests pass on the current tree.
- `sase agent recover` and the hidden `sase agent persist-recover` exist with the planned options.
- No `--epic-symbol` entries remain for sase-1qz.6.1 or sase-1qz.6.
- The core revision pin includes the Rust recovery functions.
- None of the 54 other commits since the epic started needed rewiring. The finalizer, stale-cleanup and stranded-bead changes already account for hijack recovery.

**Gaps that block the close** (confirmed in the code, not only from the review I delegated):
1. **A queued recovery never finishes on its own.** Stale cleanup only recognises a hijack record while the workspace claim still has the hijacked agent's process ID. Once the successor launches, the claim moves to the successor, so cleanup never reconciles the record. The deferred launch path also never records the recovery as done. The hijacked agent stays "resolving", its `done.json` keeps `recovery.state: pending`, and anything waiting on it stays parked until someone reruns `sase agent recover`.
2. **A crash mid-settlement is never repaired.** The settle step moves the ledger record before writing the hijacked agent's `done.json`, without first registering a pending repair. Rerunning recover just returns "already resolved" without fixing anything.
3. **A launch that provably never happened can't return the record to held.** Every resolution records launch evidence up front, so the Rust reconcile function always keeps custody. A crash before admission, or a cancelled admission, leaves the record "resolving" forever, and the explanatory message is dropped.

There are smaller issues too:
- Expired hijacks may fail their waiters instead of staying parked.
- A resumed recovery exits 2 even when it actually launched.
- A lost update when returning to held is still reported as success.
- Several crash cases the original plan required have no tests.

**Proposed plan** (`sase_plan_hijack_recovery_settlement_completion.md`, single agent, medium size): fix gaps 1–3, including a small Rust change in sase-core. It also fixes the smaller issues and adds the missing crash, queued-launch and stale-cleanup tests. Its last step, in the same turn as the code:
- re-check the epic symbols;
- close sase-1qz.6.1;
- run `just symvision`;
- mark `202611/hijack_keep_work_recovery.md` as `status: done`;
- close the parent phase sase-1qz.6 after checking its scope was delivered.

It leaves the top-level epic sase-1qz to its own land agent.

**Follow-up triage** (recorded on sase-1qz.6.1):
- **Corroborated existing beads:**
  - sase-1q0: the footprint microbenchmark over its time budget.
  - sase-1mr: the startup update toast test.
  - sase-1oy: the sudo reclaimer test.
  - sase-r2: the pipe end-to-end test. This reopened it as ready.
  - sase-1kr: the revert test's stale git lock is the same recovery path.
- **Recorded on active epic sase-1ra:** the `monkeypatch.undo()` call at `tests/ace/tui/test_log_panel_keymap.py:331` that breaks the test-isolation guard. Phase sase-1ra.5 introduced it, and it still fails on the current tree.
- **Declined:**
  - the feature-flag lint failure (a passing race);
  - the monitor follow-up test (passes now);
  - the TUI import-size concern (the budget test passes);
  - the marker-path audit (already fixed);
  - the panel-pilot sightings, which all predate that test's fix.

**Not changed:** the earlier land phase moved three exemptions (`AgentHijackConfig`, `normalize_hijack_rung`, `strip_hijack_launch_directives`) onto sase-1qz.7. That phase is still open and is expected to use them, so they stay.
