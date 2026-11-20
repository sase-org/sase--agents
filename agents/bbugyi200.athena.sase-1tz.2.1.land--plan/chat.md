# Chat History - ace-run (sase-1tz.2.1.land--plan)

- **TIMESTAMP:** 2026-11-20 08:04:57 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.2.1.land--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1tz_2_1_land__plan-261119_144814.md`
- 2. --code — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1tz_2_1_land__code-261119_144814.md`

**Plan:** /home/bryan/.sase/plans/202611/noise_epic_remaining_work.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/noise_epic_remaining_work.md`

> - **PARENT:**
>   [202611/noise_publication_digests_tui_stalls.md](202611/noise_publication_digests_tui_stalls.md)
> - **BEAD:** sase-1tz.2.1
> # Plan: finish epic sase-1tz.2.1 and land it
> ## Context
> Epic **sase-1tz.2.1** is `plan:202611/noise_publication_digests_tui_stalls.md`, which
> `sase bead read sase-1tz.2.1` shows as its PLAN. All 13 of its phases are closed. Its
> land agent verified the phases against current source and found the gaps listed below.
> Each gap is caused by this epic and required by its plan, so it is still epic work.
> The land agent already fixed three CI failures on `master` in its own commit:

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(land, clan=sase-1tz.2.1, bead=sase-1tz.2.1)
%model:@xlarge
%w(sase-1tz.2.1.2,sase-1tz.2.1.3,sase-1tz.2.1.4,sase-1tz.2.1.8,sase-1tz.2.1.11,sase-1tz.2.1.5,sase-1tz.2.1.6,sase-1tz.2.1.9,sase-1tz.2.1.7,sase-1tz.2.1.10,sase-1tz.2.1.13, for_epic=false)
%w(bead=sase-1tz.2.1.1)
%w(bead=sase-1tz.2.1.2)
%w(bead=sase-1tz.2.1.3)
%w(bead=sase-1tz.2.1.4)
%w(bead=sase-1tz.2.1.5)
%w(bead=sase-1tz.2.1.6)
%w(bead=sase-1tz.2.1.7)
%w(bead=sase-1tz.2.1.8)
%w(bead=sase-1tz.2.1.10)
%w(bead=sase-1tz.2.1.11)
%w(bead=sase-1tz.2.1.9)
%w(bead=sase-1tz.2.1.12)
%w(bead=sase-1tz.2.1.13)
You are the land agent for epic bead sase-1tz.2.1: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

Do not run `just check-full` unless this prompt or the user explicitly tells you to. File-change verification is
`just check`. A `just check` pass with a `just check-full` failure is a test-infrastructure bug, not remaining
epic work.

1. Verify. Run `sase bead read sase-1tz.2.1 -r "Need the epic scope, children, and linked plan file"`, review the epic bead's own notes, then
   run `sase bead read <child-id> -r "Need the child scope and notes"` on every child and review every child note. Confirm each note was addressed, and confirm the work honored the epic's DECISIONS, and read the
   actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
   agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-1tz.2.1, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
   genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
   proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
   task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Before
   closing, run `sase bead epic-symbols sase-1tz.2.1`. Every listed `--epic-symbol` entry is keyed to this epic
   or one of its phases and goes stale the instant that bead closes. For each entry, either resolve the symbol
   (wire it up, privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist policy) or,
   only when a still-open later bead still needs the exemption, re-key the Justfile line to that open bead. Do not
   leave that judgment for the next agent. `sase bead close` refuses while any of these entries remain. Close the
   epic with `sase bead close sase-1tz.2.1 --note "<what you verified in steps 1-2>"`. After closing, run
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
any proposal was declined, with `sase bead note sase-1tz.2.1 "..."`. The tale's final step must be this epic's
closeout, written concretely so the coder needs no other context: resolve or re-key every
`sase bead epic-symbols sase-1tz.2.1` entry, then close the epic with
`sase bead close sase-1tz.2.1 --note "<verification>"`, run `just symvision`, and set `status: done` in the
epic's plan file (the PLAN path shown by `sase bead read`); when the epic has a `parent_bead`, handle that parent
as described in the final paragraph below, using the concrete parent ID. The step-3 rules still apply in the tale:
never use `--force` merely to make the close succeed, and never use `--force` to advance a successful nested
landing. For the child-epic path: Do not include this epic's close, symvision pass, or plan-file status update
as a child phase; the child epic's `parent_bead` link is the handoff that lets its land agent resume this
interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from `sase bead read sase-1tz.2.1 -r "Need the parent link"`. If there is
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

Reading the epic plan and child beads now; next I'll check each phase's notes and commits.

Child beads reviewed; now checking the 6 non-epic commits that landed since the epic started, plus fetching origin.

The sase-core pin covers every epic core commit. Next I'm running the previously reported failing tests to see which are still red.

Two epic-caused failures remain (artifact-dir audit and doctor-detail test); I'm diagnosing them and the pre-existing drain-accounting isolation bug.

Three epic-caused failures remain on master: `OutboxGroup` symvision (2.1.7), the doctor-detail test (2.1.7), and the artifact-dir audit for `sweep_publication_scratch` (2.1.4). Looking at each now.

Fixing the doctor group detail so it keeps the row reasons and a sample last error (the grouping dropped them, which broke the test and hid the cause from users).

Adding a reviewed exemption for `sweep_publication_scratch` in the artifact-dir audit (it only removes publisher stage/backup scratch at the agents sidecar root).

Both fixed tests pass. Now I'll spawn parallel reviewers to verify phase implementations against the plan while I triage follow-ups.

Confirmed: already-quarantined rows never reach the terminal classifier in production. Checking the standing-alert `changed` comparison next.

Confirmed the remaining gaps are real and epic-caused. Next: triaging the phases' `PROPOSED FOLLOW-UP` notes via `/sase_new_task`, then planning the remaining work as a tale.

Running formatting on my edits, then launching the follow-up triage helper and `just check` in parallel.

Adding a focused assertion that a grouped issue line names the newest member's error and the row reason.

Launching the follow-up triage helper and `sase tool run check` concurrently.

Now recording the follow-up triage outcomes on the epic before planning the remaining work.

Now planning the remaining epic-caused work as a tale via `/sase_plan`.

Plan staged. Finishing through `/sase_final` so my integration edits commit before the host adopts the tale.

I haven't closed sase-1tz.2.1 yet: checking the code against the plan turned up plan-required behavior that was never built. I staged a medium-size tale that finishes that work and then closes the epic and its parent phase, sase-1tz.2.

**Verified:**
- All 13 phases are closed, and 12 phases have commits on master; sase-1tz.2.1.13 was measurement only. The before-numbers and after-install commands are on sase-1tz.2.
- `sase-core-revision.txt` (`80fcc862`) includes every sase-core commit the epic made.
- `sase bead epic-symbols sase-1tz.2.1` lists no entries.
- The 6 commits that landed since the epic started need no integration. Four just split the epic's own files, and the other two are unrelated.

**Fixed in this turn** (three failures this epic caused on master's CI, committed with the epic left open):
- `OutboxGroup` was failing symvision; it's now private.
- Grouping doctor issues by cause had dropped the reason and the actual error from each line, which broke `test_repeated_format_publication_failure_retires_and_doctor_says_drop`. Each grouped line now shows its reasons and the newest error, and I added a test for that.
- `sweep_publication_scratch` was failing the artifact-directory audit; it now has a reviewed exemption.

`sase tool run check` passed (run `611a9c52`).

**Remaining work, now in the tale:**
1. Prompt archives that were already quarantined never become terminal, because the automatic passes skip quarantined rows. The plan requires them to switch over on the next pass; there are 369 on athena and 263 on apollo.
2. A standing alert reports "changed" again whenever its error text differs only in a pid, an age or a path. That defeats the de-flap, so the fix goes in the Rust decider.
3. Two machine-wide failures (listing projects, resolving targets) still count as an error on every tick. Projects skipped by the tick budget can also be counted every tick and re-triggered while backing off.
4. Doctor never shows a live standing alert as an issue, so a failing project with no stuck rows reports OK.
5. Error accounting still loses some failures:
   - one lock failure is dropped silently;
   - a failed ring reset during digest rotation loses its count;
   - the digest keeps a Python grouping fallback that the Rust-required rule forbids;
   - some dead code is left from the old digest design.
6. The GC policy treats any leftover swap as pressure, so on athena it skipped policy collections for about 12 hours. Automatic collections then paused for 12–19 s.
7. There is no test that a multi-batch drain builds the inventory only once.

The Rust fix in item 2 reaches sase only after the core pin is ratcheted past it; the tale's closeout doesn't wait for that.

**Follow-up triage** (outcomes recorded in a note on the epic):
- **New tasks:** sase-1u4 (tests in the drain-accounting file break each other when run alone), sase-1u5 (sase-1rb remedy (b)), sase-1u6 (TUI file reads still on the main thread), sase-1u7 (a deterministic failure in one slow benchmark), sase-1u8 (video-frame tests fail on master CI because the runners have no ffmpeg).
- **Corroborated with +1:** sase-1tn, sase-1s4, sase-1kr, sase-1ty.
- **Closed:** sase-1tw (the skill-use cache fix is demonstrated) and sase-1u3 (already fixed on master).
- **Notes added:** sase-1tx and sase-1nc.
- **Declined:** the spawn `ModuleNotFoundError` report for `test_concurrent_error_appends_are_atomic_and_lossless`, which passes on master and in CI.

Live after-install acceptance still waits on a human install.
