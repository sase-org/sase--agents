# Chat History - ace-run (1fz--plan)

- **TIMESTAMP:** 2026-11-25 10:14:58 EST
- **MODEL:** claude/opus
- **AGENT:** 1fz--plan

**Plan:** /home/bryan/.sase/plans/202611/stranded_toast_flood.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/stranded_toast_flood.md`

> # Stop Stranded-Work Toast Floods From Artifact-Index Lock Contention
> ## Problem
> The ACE TUI periodically shows a wall of toasts such as
> `⚐ sase-10h is stranded: --plan ended without closing the bead; nothing resumes it.`.
> They name beads that have been stranded for weeks, not new ones. In the `sase` project
> there are about 137 stranded beads, so every flood is about 137 toasts. While a flood is
> happening, the ⚐ row badges and the stranded count also blink off for one report cycle.
> ## Root Cause (reproduced)
> 1. `session_record_cache()` in `src/sase/bead/_stranded_facts_snapshot.py` queries the
>    artifact index with `lock_timeout_seconds=DEFAULT_READ_LOCK_TIMEOUT_SECONDS` (0.05

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase I keep getting these notifications periodically. See the
~/tmp/screenshots/20261125_100243.png screenshot for context. Is this something we
can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Those toasts come from the stranded-work notifier (`_stranded_toasts.py`). I'm checking why old, long-stranded beads keep getting announced again as if they were new.

Still diagnosing. The toast logic announces any bead that wasn't in the previous report, so I'm looking for what makes long-stranded beads drop out of one report and come back in the next.

I'm reading the core reducer now to see how it classifies a bead when the artifact index can't be read.

Root cause is confirmed and the fix belongs entirely in this repo; the Rust reducer's `unknown` verdict is correct. Next I'll read the TUI memory note, then write the plan.

I have enough to write the plan. Invoking the planning skill now.

Writing and validating the plan file now.

The plan is staged. Finishing the turn through `/sase_final`.

Yes, this should be fixed. It's a bug, not 137 beads newly getting stranded. I've proposed a plan and it's waiting for your approval.

**What's going wrong**

- **The beads aren't new.** `sase-10h`, `sase-10w`, `sase-110.7` and the rest have been stranded for weeks. The `sase` project has about 137 stranded beads.
- **Why they drop out.** To build the stranded report, the TUI reads the artifact index with a 50 ms lock timeout. The agent loader and the index-refresh code in the same TUI hold that lock often. When the read times out, the stranded-bead classifier (in sase-core) marks every affected bead `unknown`. The TUI then accepts that partial report in place of the complete one, so the stranded list briefly goes empty.
- **Why they come back as toasts.** The toast logic only compares each report with the one before it. When the next uncontended report lists the beads again, every one looks "newly stranded" and gets its own toast.

**Reproduced.** I held the lock in a thread and built the `sase` report:
- The report came back with 0 stranded and 193 beads marked unknown.
- The next normal report re-announced 137 beads in the order `sase-10h, sase-10w, sase-10w.5, sase-110.7, sase-112, sase-116.5, …`, which is exactly the stack in your screenshot.
- The ⚐ row badges and the stranded count also blink off during each of these cycles.

**The plan** (one agent, size medium, all in this repo):
1. **Flag incomplete reports.** Mark a report as degraded when the index couldn't be read.
2. **Keep the last complete report.** A degraded report never replaces a complete one; the next refresh tick retries. This stops the badge and count flicker too.
3. **Toast each stranding once.** Toasts are tracked by the bead's last turn instead of by "in the previous report". A bead flickering in and out of the report stays quiet, while a bead that strands again after a new turn still gets a toast. No toast baseline is set from a degraded report.
4. **Tests and a one-line docs addition** covering the flicker-and-return case from your screenshot.

**Decision for you:** whether a burst of more than three newly stranded beads should collapse into one summary toast (`⚐ 12 beads newly stranded: a, b, c (+9 more).`). The default is yes, so a real mass stranding, like after a host reboot, doesn't bury the screen.

The plan leaves the Rust core and the 50 ms lock timeout unchanged. `sase doctor` isn't affected, because it runs in its own process where nothing else holds the lock.
