# Chat History - ace-run (sase-1tz.2.1.land--code)

- **TIMESTAMP:** 2026-11-20 09:09:21 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.2.1.land--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1tz_2_1_land__plan-261119_144814.md`
- **2. --code** — `~/.sase/chats/202611/gh_sase_org__sase-ace_run-sase_1tz_2_1_land__code-261119_144814.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202611/noise_epic_remaining_work.md

The above plan has been reviewed and approved. Implement it now.


## Response

Reading the approved plan's reference notes, then implementing its six work items and landing the epic.

Spawning parallel helpers for the six work items after a quick environment check.

Splitting into five parallel helpers by file area (prompt terminal sweep + inventory test, standing alerts Rust/job, doctor, axe error accounting, GC policy); I'll integrate, verify, and land.

All five helpers finished. Reviewing the integrated diff now.

Reviewed items 1 and 2; checking how job diagnostics surface, then the doctor/axe/GC diffs.

Doctor change looks right. Adding the standing-alert rules sentence to hood-sync.md that the item-2 helper flagged.

All diffs reviewed and consistent with the plan. Running `just fmt`, a line-budget check, then the full `sase tool run check`.

The only failure is mine: `hood-sync.md` is now 6117 words, over the 6000-word reference cap. Tightening the added prose.

Docs contract passes now. The GC runbook grew 34 words on a page flagged "may not grow"; trimming it back to flat.

The runbook is now flat (16229 vs 16230 words). Rerunning `sase tool run check`.

`sase tool run check` passed (run `d3adc7ab6cd66e963ccabbaf4b676910`, about 20 min). Getting the scoped-test count, then moving to the landing steps.

Check passed; the scoped lane escalated to the full suite and it all passed. Epic-symbols list is empty. Now the bead updates: an evidence note on sase-1nc, then closing the epic.

Closing the epic also auto-closed its parent phase sase-1tz.2. I'll still do the plan's verification of that phase and record it as a note. Running `just symvision` first.

Symvision is clean. Now setting the epic plan's frontmatter to `status: done`.

Now verifying phase sase-1tz.2's scope and its notes #1–#8 before recording the verification.

All plan steps are done. Finalizing the turn.

I've implemented all six items of the remaining-work plan and closed epic sase-1tz.2.1. The full `sase tool run check` passed (run `d3adc7ab6cd66e963ccabbaf4b676910`; its test lane ran the whole suite). The host commits the sase, sase-core, and plans changes after this turn ends.

**What changed**
1. **Quarantined prompt archives now reach the terminal state.** Each automatic publisher pass re-checks up to 25 quarantined prompt rows per project. Rows the Rust classifier calls unrecoverable become terminal with one audit row and their pool files released. The re-check never charges, publishes, or unquarantines a row; if a row's source still exists it stays quarantined. The athena (369) and apollo (263) backlogs should drain over a few passes after install.
2. **Standing alerts no longer report on volatile detail.** In sase-core, only a change of key, failure kind, or error class counts as `changed`; that repo's check passed (run `ccbc1dc8…`). This part reaches sase only after the core pin ratchet. In sase:
   - project-listing and target-resolution failures are now alerts on `*publisher*`;
   - a project skipped by the tick budget or by backoff is no longer counted every tick;
   - a skipped project's doorbell rings only when its alert is due.
3. **Doctor** now warns on a live standing alert that has no stuck rows. The count stays the same when only attempts go up.
4. **Error accounting:**
   - lock-open and ring-reset failures are now counted instead of lost;
   - the Python grouping fallbacks are gone;
   - the dead `last_error_digest_ts` code and the old `errors=` digest path are deleted.
5. **GC policy:** only paging counts as pressure (a high major-fault rate, or VmSwap growing by more than 16 MiB between samples). A stable leftover VmSwap no longer defers sweeps. Backstops can be held at most 10 minutes, and automatic gen-2 pauses now refresh the cost estimate.
6. **New test:** a drain with more than 25 rows builds the inventory once, and builds it again if HEAD moves between batches.

Each item has the tests the plan named, and the docs are updated. `hood-sync.md` at first went over its 6000-word limit, so I shortened the added prose. The perf runbook ended up the same length as before.

**Things that differ from the plan**
- **sase-1tz.2 closed itself** when I closed the epic, before I verified it. I checked its five work areas and notes #1–#8 afterwards, and added a note saying live after-install acceptance is still pending your install (the commands are in note #8). Epic sase-1tz is untouched.
- **New `prompt_terminal_sweep.json` file** (not in the plan): it records when each row was last checked so rows are re-checked at most hourly. Without it, the same 25 rows that still have their source would be re-read every pass and the rest of the backlog would never be reached.
- **No sweep on explicit `sase agent sync`:** only the background publisher pass runs the sweep.
- **Rust test file split:** the sase-core change also split a 1,755-line test file into two modules.
- **Possible gap in the GC fix:** once a pause is known and exceeds 2 s, the cost gate still waits for 15 idle minutes by design. Athena's automatic gen-2s ran 12–19 s, so `rss_backstop` may still wait a long time. I put this in the evidence note on sase-1nc to check after install.

Symvision is clean and the epic-symbol list is empty. The epic plan is marked `status: done`.
