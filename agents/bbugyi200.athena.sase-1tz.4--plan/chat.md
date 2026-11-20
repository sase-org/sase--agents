# Chat History - ace-run (sase-1tz.4--plan)

- **TIMESTAMP:** 2026-11-20 13:59:56 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.4--plan

**Plan:** /home/bryan/.sase/plans/202611/hygiene_gateway_notifications_retention.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/hygiene_gateway_notifications_retention.md`

> - **PARENT:**
>   [202611/notification_log_audit_fixes.md](202611/notification_log_audit_fixes.md)
> # Plan: Gateway checkpoint fix, notification hygiene, and retention sweep (items 11–13)
> This child epic implements phase `hygiene` (**sase-1tz.4**) of parent epic **sase-1tz**,
> `plan:202611/notification_log_audit_fixes.md`. It covers items 11–13, which are audit
> findings F11 (gateway WAL checkpoint and snapshot waits), F12 (notification hygiene),
> and F13 (log and state retention).
> ## Read first (every phase)
> - **Audit.** The source of truth is
>   `research:202611/apollo_athena_sase_notification_and_log_audit/apollo_athena_sase_notification_and_log_audit.md`

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(4, clan=sase-1tz, bead=sase-1tz.4)
%model:@xlarge
%w(sase-1tz.3, for_epic=false)
%w(bead=sase-1tz.3)
Can you complete the work for bead sase-1tz.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.4` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.4` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.4 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.4 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
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

Reading the phase scope and existing state before writing a child epic plan for sase-1tz.4 (items 11–13).

Status: no earlier agent worked this phase, so I'm surveying the code for items 11–13 before writing a child epic plan. Next I'll read the audit and send parallel code explorers.

Status: the code survey is back. Now I'm checking a few prior decisions that limit the retention reapers (sase-zw notes) and the triage "quiet-task-beads" rule.

Status: design inputs are nearly complete. Checking three last facts (notification `silent` field, Telegram use of `action_data` prompts, how the gateway binary ships) before writing the plan.

Status: I have what I need for the phase graph. Last check: whether any memory note would become false after these changes (dispatch/ace/tui notes).

Status: survey done, no memory note becomes false. Writing the child epic plan now (13 phases across gateway, notification hygiene, and retention).

The plan is staged. Finishing the turn through `/sase_final`.

I've written and submitted a child epic plan for sase-1tz.4 (items 11–13). It is staged for your review: no code has changed yet, and the bead stays in progress. No earlier agent had worked this phase. The plan passed validation with no warnings, and the turn needed no commit.

**Phases.** There are 13, one coding agent each. All are medium except `wal_busy`, which is small. Seven can start at once; six wait on another phase.
- **Gateway (item 11):**
  - `wal_busy`: a busy SQLite checkpoint reports "busy" instead of failing on the `-1` result, and the gateway's checkpoint after each snapshot build waits less.
  - `gateway_swr`: an expired cached snapshot is served immediately while one rebuild runs in the background. An empty cache still waits briefly and can time out with a 504.
- **Notifications (item 12):**
  - `attention_key`: one remote-attention row per request.
  - `blob_store` → `blob_adopt`: oversize payloads move to sidecar files. The first phase leaves default behavior unchanged; the second updates every reader (TUI, Telegram, mobile) before turning on the 8 KB limit.
  - `wait_blocker` → `waiter_expire`: one notice per failed blocker, plus the one-key expire action your `blocked_waiters = offer` decision chose.
  - `triage_volume` → `gate_reconcile`: one triage notification per bead, and settled gate bundles get deleted after a horizon.
  - `notify_quieting`: silent file-hook successes, a dedup key for workspace-rescue, a size floor on prune nudges, and no more no-op claim-ledger rows.
  - `state_refresh_memo`: agent_state_refresh logs an unchanged warning once instead of every pass.
- **Retention (item 13):**
  - `log_horizons`: the existing 14-day tool-run log retention runs on an hourly schedule instead of only under disk pressure, and `tui.log` also rotates by age.
  - `clutter_reapers`: fixes the two leaks behind the `.log.lock` files and the registry `.tmp` files, then cleans up the backlog.

**Where the audit and live data differ:**
- **`interaction_requests/` dirs:** these are mostly settled, not orphaned. Of athena's 5,104 triage dirs, 4,461 are cancelled and 217 answered. The 426 still pending all have live notifications. The real problems are that nothing deletes settled bundles, and that every bead edit cancels and recreates its triage gate (2,139 times). The plan targets both.
- **The "triage-volume fix" your `quiet-task-beads` rule waits for:** it isn't defined anywhere. The plan treats it as stopping that per-edit cancel-and-recreate churn.
- **Already in place:** error-digest pruning (from the noise phase), and `artifact_run_prune` is unblocked on athena. Both phases only verify these.

**Two choices for you in the review:**
- **`index_backups`, default `report`:** the 222 MiB index backup on athena is listed for you to delete by hand through a confirmation prompt, and nothing deletes backups automatically. I chose this because an earlier disk-cleanup epic (sase-zw) declined deleting backups, and no SASE code writes these files. The alternative is a reaper that deletes backups older than 30 days.
- **`quiet_triage_rule`, default `remove`:** once tests show one notification per bead, the phase deletes the `quiet-task-beads` rule from the chezmoi source, as the rule's own text asks. It takes effect only when you run `chezmoi apply`.

This epic authorizes no memory edits; none of the memory notes I checked becomes false.
