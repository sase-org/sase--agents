# Chat History - ace-run (sase-ys.2)

- **TIMESTAMP:** 2026-09-09 08:29:39 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ys.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-ys, bead=sase-ys.2)
%model:@medium
%auto
%w:sase-ys.1
%w(bead=sase-ys.1)
Can you complete the work for bead sase-ys.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-ys.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-ys.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ys.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the SASE skills this phase needs so the work stays on the assigned bead.

I'll load the bead details, beads/xprompt memory, and glossary terms next so the phase work matches the design.

The phase is ACE/LSP star-alias parity after the core ratchet. I’ll read the plan, parent epic, and prior phase next.

I’ll open `sase-core` through the repo skill and inspect the current pin, ACE shortcut path, and how core revisions are ratcheted.

Phase 1 is in core. Next I’ll confirm the landed SHA, how the revision ratchet works, and the current ACE/LSP call sites.

Phase 1 is on core HEAD and PyPI still lacks the new binding, so I’ll pin that SHA, switch ACE to the shared filter, and leave the published floor unchanged.

That filterText assertion is leftover junk. I’ll replace it with a proper ACE-query check.

Install finished. I’ll confirm the Python binding and LSP binary actually come from the phase-1 core, not a stale 0.32.53 wheel.

`just check` passed. Next I’ll inspect leftover epic symbols, then close only this phase bead.

Completed **sase-ys.2** (Pin the core and prove ACE/LSP parity) and closed that phase bead only.

**Core pin.** `sase-core-revision.txt` now tracks `cb669ec96526`, the landed star-alias contract. The published `sase-core-rs` floor stays `>=0.32.50,<0.33.0`: PyPI’s latest is `0.32.53`, and `filter_model_alias_shortcut_entries` has no containing release yet.

**ACE.** Shortcut rows go through the shared Rust alias-only filter via a thin wire adapter. Acceptance still revalidates with `plan_model_alias_shortcut_edit`. Menu presentation is unchanged.

**Parity.** The real-binary LSP harness now exposes `isIncomplete`, `preselect`, label details, multiline UTF-16 positions, and raw text edits. Installed-binary tests compare ACE and LSP on alias names/order, whole-token edits and caret, whitespace/Unicode/CRLF, empty/no-match ownership, protected stars, missing/malformed catalogs, and unchanged `%model:` rows.

**Docs.** `docs/editor.md`, `docs/xprompt.md`, and `docs/ace.md` document `*alias`, canonical `%m:@alias` expansion, trigger boundaries, and that `auto_directive_menu` remains ACE-only.

**Verified.** 119 focused tests plus `just check` (lint + scoped suite, escalated for the core pin). `sase bead epic-symbols sase-ys.2` reported no leftovers. Parent epic `sase-ys` was left open.
