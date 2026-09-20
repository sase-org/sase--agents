# Chat History - ace-run (sase-14l.1)

- **TIMESTAMP:** 2026-09-20 17:16:20 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-14l.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-14l.1, bead=sase-14l.1)
%clan(sase-14l, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@small
%auto
Can you complete the work for bead sase-14l.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14l.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14l.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14l.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Implementing the Rust matcher now.

Add a test after the completions-matching-agents test.

Submitting the commit declaration for the sase-core change now.

Bead sase-14l.1 is closed. The sase-core notification store now dismisses `epic-launch` and `monitor-settlement` rows when the agent row they name is acknowledged. The commit declaration for sase-core was accepted, and the host finalizer does the actual commit.

- **Matching rule:** a settlement row matches only on an exact `(cl_name, raw_suffix)` pair. There is no `cl_name`-only fallback, because `cl_name` on these rows is the patch name shared by every agent in the project. A comment in the code explains this so nobody "fixes" the difference from the completion matcher.
- **Where it applies:** `DismissAgentCompletionsMatchingAgents` now dismisses a row if either the completion matcher or the new settlement matcher accepts it. The already-dismissed skip and the matched/changed counts are unchanged.
- **Left alone:** the existing completion matcher and the agent-less `DismissAgentCompletions` arm are untouched, and there is no new wire variant.
- **Tests:** I added three parity tests in `notification_store_parity.rs` covering each case listed in the plan. They also pin that the agent-less arm leaves settlement rows alone.
- **Verification:** `cargo fmt` is clean, `notification_store_parity` passes (62 tests), and sase-core's `just check` exited 0.

`sase bead epic-symbols sase-14l.1` reported no epic symbols. I did not touch `sase-core-revision.txt`; moving the pin belongs to the next phase, sase-14l.2.
