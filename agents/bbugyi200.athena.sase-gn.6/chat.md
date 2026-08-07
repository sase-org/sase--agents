# Chat History - ace-run (sase-gn.6)

- **TIMESTAMP:** 2026-08-06 21:17:12 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gn.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-gn, bead=sase-gn.6)
%model:@medium_phase_worker
%auto
%w:sase-gn.4
%w(bead=sase-gn.4)
Can you complete the work for bead sase-gn.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gn.6 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gn.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead description.

Now let me write the shared duration helper.

Now wire it into validation and notification construction.

Now the notification construction in `service.py`:

That sed mangled it; let me fix directly.

Now the adapter registration and side effects:

Now the `validate_selection` hook and the adapter entry:

Two script artifacts to fix:

Now the bead_snooze payload and spec validators:

Now let me write the tests.

Phase **sase-gn.6 (BeadSnooze wake gate)** is complete, committed as `17fcbb485`, and the bead is closed.

**What landed**

- `src/sase/bead/snooze_gate.py` — the `bead_snooze` gate contract, mirroring `task_gate`: same payload fields, command wrapper, and preview renderer, with a snooze callout prepended (who deferred it, until when, +1 progress, reason). All rendered fields are persisted absolute instants so validation can still reconstruct the preview byte for byte as it ages.
- Options: **close** (primary, optional feedback; empty feedback uses the preset `"Snoozed until … with no new evidence; closing as stale."`), **ready** (cancels the snooze and appends the preset note — it deliberately does *not* raise the TaskTriage gate; the reconciler owns that), **snooze** (required feedback carrying a new duration).
- **Born snoozed (D2)**: `presentation.snooze_until` is validated in `presentation.py`/`validation.py` and applied in `_build_notification`, so the notification is created `muted=True, snooze_until=<wake>` in one atomic append. It's a general capability, not bead-specific.
- `src/sase/bead/snooze_duration.py` — the shared `"<duration> [+<N>]"` parser phases .7/.8 will reuse; it layers days onto `parse_duration`, which has no day unit.
- The TaskTriage payload parser is now parameterized by error code/label and reused for the shared task fields; `close_record_payload` was made public for the same reason.
- `BeadSnooze` joins the priority actions; `PRIVILEGED_GATE_ACTIONS` picks it up from the adapter registry automatically.

**Two judgment calls, both recorded as `PROPOSED FOLLOW-UP:` notes on the bead**

1. The plan wanted the unparsable-duration check to "fail the option command", but an option command can't see the feedback text. I added a general `GateAdapter.validate_selection` hook called by the executor right after feedback normalization — *before* the response is persisted — so a typo leaves the gate pending, which is the property the plan was actually after.
2. The plan asked to add `BeadSnooze` to the mobile priority set in `sase-core`, on the premise that it parallels Python's. It doesn't: `mobile.rs`'s `is_priority_gate` covers only plan/epic/question/launch, and `TaskTriage` maps to `Unsupported`. I mirrored TaskTriage exactly (Python-only), so no core change was needed; whether bead gates should be mobile-priority is a separate decision covering both kinds.

`just check` is green. Along the way three unrelated tests each flaked once under the parallel lane and passed in isolation — noted on the bead as well; the box is running several epic agents concurrently.
