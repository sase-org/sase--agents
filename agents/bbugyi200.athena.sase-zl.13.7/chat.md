# Chat History - ace-run (sase-zl.13.7)

- **TIMESTAMP:** 2026-09-12 07:15:30 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-zl.13.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-zl.13, bead=sase-zl.13.7)
%model:@medium
%auto
%w:sase-zl.13.6
%w(bead=sase-zl.13.6)
Can you complete the work for bead sase-zl.13.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zl.13.7 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zl.13.7`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zl.13.7 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills that govern this phase.

The bead is a recovery-and-receipts repair. Next I’ll read the epic plan and the bead page so the implementation stays aligned.

I’ll pull the parent plan, landing evidence, and the current recovery/finalizer code so the completion phase has a solid baseline.

The recovery launcher still uses the incomplete two-argument call. I’ll inspect the production launch path, finalizer controller, and prior phase work next.

sase-zq already landed bead-action requirements. I’ll check whether host completion still carries those through the live context and declaration path.

I have a clear picture of the gaps. Next I’ll fix host adoption, recovery kwargs, and receipt completeness, then add controller-level tests.

I’ll rewrite host completion so recovery uses the real launcher signature, adoption is atomic, and receipts cover every required repository.

The controller path is working. I’ll adjust the drift assertion and make bead-action validation work even when the installed wheel lacks the new binding.

`host_completion.py` is over the 1000-line limit, so I’m splitting receipt and snapshot helpers into a sibling module.

Symvision will flag helpers that nothing outside tests imports, so I’m making those state-module helpers private.

`just check` failed on four tests that look unrelated to host completion. I’ll inspect them before closing.

Closed **sase-zl.13.7** (Repair real host-finalizer recovery and receipts). The parent epic was left open.

Host completion now uses the real follow-up launcher, adopts under one lock, and only finishes after every required repository and later finalizer has a clear receipt.

**Recovery launcher.** `_recover` now passes the production keyword-only arguments (`monitor_state`, `exit_code`, `elapsed_seconds`, `capture`, `project_name`). A two-argument callback raises `TypeError` instead of hiding the integration bug. Settlement forwards `capture`, `timeout_kind`, and `transfer_from_pid` into that path.

**Atomic host adoption.** Host delivery moves `pending → reserved → acknowledged` under a single delivery-store lock as `host-completion`, on the original workspace. Degraded workspace fallback is refused.

**Receipts.** Completeness requires every declared commit repo (`result=ok` plus sha) and later finalizer instances independently. One successful repo no longer completes the run. Ambiguous external actions go to `needs_attention` without retry. New obligations or remaining dirty trees after finalizers go to one recovery, with receipts kept.

**Bead action.** If the finalizer context has an assigned bead, commit decisions must include `bead_action` (`keep` or `close`), matching the sase-zq.1 contract.

**Verified.** 15 host-completion tests passed, including real controller/declaration adapters, zero model calls on success, stale/missing/unsupported/drift each launching one recovery, and a two-repo crash that retains the first receipt and never marks completed. `just check` lint gates passed. The scoped suite escalated to the full suite because `finalizer_facade.py` grew a bead-action helper; 40903 passed and 4 failed under load (fakey timeout, propose-report `python3` subscript). Those four passed on an isolated rerun. `sase bead epic-symbols sase-zl.13.7` had no leftovers.
