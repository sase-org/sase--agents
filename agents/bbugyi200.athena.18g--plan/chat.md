# Chat History - ace-run (18g--plan)

- **TIMESTAMP:** 2026-11-05 06:41:51 EST
- **MODEL:** claude/opus
- **AGENT:** 18g--plan

**Plan:** /home/bryan/.sase/plans/202611/stranded_adopted_staged_handoff.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/stranded_adopted_staged_handoff.md`

> # Stop delivered staged handoffs from owning beads forever
> ## Problem
> A phase agent that finishes without closing its `in_progress` bead should show **⚐
> STRANDED** in ACE. Agent sessions that ever handed off to a monitor, gate, or plan
> successor never do. Real example: `bob-cli-h4.4` (bob-cli project). Eleven turns
> (`--plan`, `--mon`, `--1`, `--mon-0`, … `--5`) all finished by 2026-11-04 19:43 EST, and
> the bead was still `in_progress`. The Agents tab showed the row as plain `DONE`. There
> was no STRANDED overlay, no stranded marker on the clan, and its waiters
> (`bob-cli-h4.5`, `bob-cli-h4.6`, `bob-cli-h4.land`) showed no stranded wait target.
> ### Root cause

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase I though that the `bob-cli-h4.4` sase agent should be mrked as stranded since it
did not close its bead. See the ~/tmp/screenshots/20261105_062601.png screenshot for
context. Am I misunderstanding the way this works? If not, use your /sase_plan skill to plan the appropriate changes.
 %m:@xlarge

## Response

I'm looking into how SASE decides that an agent's bead is "stranded". Next I'll open the Rust core, where that verdict is computed.

The bead is still `in_progress` with an assignee, so it should be a stranded candidate. I'll run the reducer directly to see what verdict it gets.

The reducer returns `unknown / no_records`: the collector found no session records for assignee `bob-cli-h4.4`. Next I'll check what the agent's artifacts actually record as their session and name.

Only 2 of the agent's ~15 turns mention `bob-cli-h4.4` in their metadata. I'll compare their session and name fields with the other turns.

The user relaunched `bob-cli-h4.4` at 06:31, after the screenshot. The original 11 turns' artifact directories no longer show up under `ace-run`. I'll check whether they were archived or moved.

I'm tracking down where the original `bob-cli-h4.4` session turns went. Its root artifact directory (`20261104150015`) is missing from disk.

The session-successor artifacts for the other phases (`h4.1` etc.) are also missing locally, so I'm checking how successor turns are stored before drawing conclusions.

Next I'll check whether retrying an agent removed the old `h4.4` turns' artifacts, since that affects what evidence is left.

A scheduled reconciler (`reconcile_staged_handoffs`) does exist, so I'll check whether it is meant to clear adopted stages.

Diagnosis done. You're reading it correctly: `bob-cli-h4.4` should have been flagged stranded, and a reducer bug stopped it. I'll write the plan with `/sase_plan` now.

I'm writing the plan file now: one tale, spanning sase-core (reducer and wire) and sase (collector, tests, docs).

The plan proposal is staged. I'm checking the host's final context to see whether a commit declaration is needed.

You're reading it right: `bob-cli-h4.4` should have been flagged ⚐ STRANDED. A classification bug kept it from happening. I've written a fix plan and staged it for your approval.

## Why it wasn't flagged

When I ran the stranded-work classifier (in the Rust core, `sase-core`) on similar live beads, it returned `owned` with reason `handoff`. Those beads are already in the state you expected to be flagged. A bead marked `owned` can't become stranded, and the Agents tab only draws the STRANDED overlay for the `stranded` state.

Here's why it says `owned`:

- **The rule:** any session turn that still has a staged-handoff file (`.sase_handoff_staged.json`) counts as a live owner of the bead. The rule ignores whether that handoff already completed.
- **The leftover files:** after a handoff completes, the host keeps the staged file next to a receipt marked `adopted`, because the recovery service needs both. Nothing ever deletes them.
- **The result:** every finished turn that ran `sase monitor start`, a gate, or `sase plan propose` keeps "owning" its bead forever. `h4.4`'s `--plan` and `--1` through `--4` turns all handed off to monitors, so the bead stayed `owned` after `--5` ended without closing it.
- **A test pins this:** a Rust test asserts that "a later reconciler clears" these files. No such cleanup exists; the reconciler only delivers handoffs.

## Evidence

- `h4.4`'s own artifact directories were deleted after your screenshot, so I couldn't run the classifier on it directly. Its published turn records show the same handoff pattern.
- On current data, `bob-cli-h8.7` and `sase-1qz.6.1.4` have every turn finished but are classified `owned`/`handoff`.
- Ignoring completed handoffs turns them into `stranded/unclosed` and `stranded/kept`. Beads with a live monitor still running stay `owned`.

## The plan

It's a single medium-sized tale, `sase_plan_stranded_adopted_staged_handoff.md`:

- **Collector (`src/sase/bead/stranded_facts.py`):** record a new `staged_delivered` fact. It is true when the handoff has an `adopted` receipt and its successor was actually delivered. The check reuses the recovery service's existing helpers so the two definitions can't drift apart.
- **Classifier (`sase-core`):** a staged handoff counts as ownership only until it is delivered. After that, the successor owns the bead through its own session turn, if it's still running; otherwise the normal stranded rules apply. Malformed, held or undelivered handoffs still count as owners, as today.
- **Tests and docs:** update the Rust test that pins the old behavior and add one shaped like `h4.4`. Add Python collector tests and a short note in the "Stranded beads" section of `docs/reference/work-units/bead-lifecycles.md`.

## A second bug, left out of the plan

The same check turned up another case: a monitor turn that has finished but still shows a follow-up as pending keeps owning its bead (`sase-1ih.2`, `sase-kp`, `sase-ru.6`, `sase-s5`). Its cause isn't confirmed yet, so the plan has the implementer file a separate task for it rather than fix it here.
