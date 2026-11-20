# Chat History - ace-run (sase-1tz.3--plan)

- **TIMESTAMP:** 2026-11-20 09:19:00 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.3--plan

**Plan:** /home/bryan/.sase/plans/202611/defects_wire_swap_telegram_bundles_triage.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/defects_wire_swap_telegram_bundles_triage.md`

> - **PARENT:**
>   [202611/notification_log_audit_fixes.md](202611/notification_log_audit_fixes.md)
> # Plan: Targeted defect fixes (items 6–10)
> This child epic implements phase `defects` (**sase-1tz.3**) of parent epic **sase-1tz**,
> `plan:202611/notification_log_audit_fixes.md`. It covers items 6–10, which are audit
> findings F6 (`prompt_prose` wire mismatch), F7 (update races), F8 (Telegram transport),
> F10 (Codex bundle cap), and F9 (triage request-id retry).
> ## Read first (every phase)
> - **Audit.** The source of truth is
>   `research:202611/apollo_athena_sase_notification_and_log_audit/apollo_athena_sase_notification_and_log_audit.md`

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(3, clan=sase-1tz, bead=sase-1tz.3)
%model:@xlarge
%w(sase-1tz.2, for_epic=false)
%w(bead=sase-1tz.2)
Can you complete the work for bead sase-1tz.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.3` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.3` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.3 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.3 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

Reading the phase bead's notes and how sibling phases were structured before planning.

Exploring current code state for items 6–10 to ground the child epic plan.

Item 6 is mapped. Now opening sase-telegram and bob-cli, then fanning out research on items 7–9 while I check item 10.

Research on items 7–9 is back. Checking item 10 (bead_task_triage request-id conflict) myself.

Item 10 mapped. Now checking open beads that overlap these items (and what sibling phase sase-1tz.4 is doing in the same files).

Checking the web roster renderer to decide how the trim (codex_bundle = trim) should work.

Before proposing a plan whose trim phase would regenerate memory web descriptors, I need the memory-write routing guidance.

Now looking at the sibling child plan's raw frontmatter to match the schema, then I'll write the plan.

I have what I need for all five items. Quick check on explicit-instruction feature flags before writing, since the bundle phases must not disturb them.

Writing the child epic plan now.

The plan validates cleanly. Submitting it.

I wrote a child epic plan for sase-1tz.3 (items 6–10) and submitted it for your approval. Nothing is implemented yet: after approval, separate coding agents run the 11 phases, and the epic's land agent closes sase-1tz.3. The bead had no notes from an earlier attempt, so this is the first pass. The plan passed validation with 0 warnings, I changed no repository files, and the host said no commit declaration was needed.

**The 11 phases**
- **`prose_wire` (item 6):**
  - Adds `prompt_prose` as a link origin in sase-core and moves the sase-core pin.
  - Puts every origin sase writes into one Python constant, with a test that checks each one against the real `sase_core_rs.artifact_link_validate_row`. A future origin sase-core doesn't accept will fail that test.
  - The "wire is stale: expected 3, got 4" message comes from an existing version check that fires during updates. Those update failures belong to item 7.
- **`swap_repro` → `swap_chop_guards` → `swap_launch_guards` (item 7.1–7.2):**
  - First, a test harness simulates an install in temp directories and reproduces each failure mode. Modes that still fail become strict xfails for the next two phases to fix.
  - Then scheduler jobs, launches and finalizers that overlap an install wait and retry instead of failing.
  - The SIGBUS crashes get fixed only if the harness reproduces them. A full versioned-runtime redesign becomes a follow-up note, not part of this work.
- **`prebuild_miss` (item 7.3):** a prebuilt-artifact cache miss exits 0 and is recorded as a miss, not a failure. The prebuild producer also stops ignoring `just install` and `just install-dev`.
- **`tg_transport` → `tg_degraded`, plus `tg_scope` (item 8):**
  - Telegram falls back to plain text only when Markdown fails to parse, and retries one chunk at a time without resending chunks already delivered.
  - Credential and network outages record one degraded state with one notice per state change, instead of a traceback on every attempt.
  - The outbound job moves into the athena-only config in chezmoi.
- **`bundle_trim` → `bundle_gate` (item 9, under the approved "trim" decision):**
  - When a bundle would exceed a provider's size cap, compilation first drops the summaries of superseded entries in long lists like `decisions`. If that isn't enough, it shortens whole lists, largest first.
  - bob-cli's Codex bundle is 36,225 bytes against roughly 32,678 bytes of usable budget, and the first step alone should bring it under.
  - Bundles already under the cap don't change, so no memory files or the committed `AGENTS.md` change. That's why the plan has no memory decisions.
  - A `sase doctor` check covers every enabled project, and a `just check` test keeps sase's own bundle under every cap.
- **`triage_conflict` (item 10):** on `request_id_conflict`, bead triage cancels the stale gate, moves to the next generation, saves it, and recreates the gate in the same pass.

**Choices I made myself:**
- The compaction is a compile-time projection, so descriptor files on disk stay full. I picked this so nothing in memory or `AGENTS.md` has to change.
- Splitting item 7 into reproducer-first phases follows the parent plan's instruction to build the reproducer before choosing a design.

**Overlap:** sase-1tz.4 (hygiene) also edits the bead triage script, so `triage_conflict` keeps its change inside the gate-creation code.
