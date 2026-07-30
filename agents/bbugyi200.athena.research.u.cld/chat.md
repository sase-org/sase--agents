# Chat History - ace-run (research.u.cld)

- **TIMESTAMP:** 2026-07-30 12:13:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.u.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260730_120101.md`

## Prompt

%id(cld, clan=research.u) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've been thinking a lot lately about ways I can improve sase beads. Can you do some research with this goal in mind? End your analysis with a list of ranked recommended improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of sase beads.

Prior research exists. Let me read it to build on rather than duplicate.

Both prior reports are here; the 2026-07-25 one supersedes the 07-14 one. Today is 07-30, so my job is to measure what actually changed in the last 5 days and find what's still open. Let me gather live data.

Major changes since 07-25: store grew 2,014 → 2,417, and **open beads are back to 0**. Let me dig into what shipped and what's still open.

The `plans:` prefix means logical refs shipped — my check was wrong. Let me re-measure correctly and read the prompts.

This is turning up a significant structural finding. Let me verify it carefully.

Let me verify one precision point before writing.

All measurements done. Writing the report.

Written to `sase/repos/research/202607/sase_beads_improvements_20260730.md`.

## What I found

I started by reading the two prior beads reports (07-14 and 07-25) so this would build on them rather than repeat them, then re-measured everything against the live store, event streams, plan sidecar, source, and upstream.

**The 07-25 report's top-10 is mostly done.** In five days: `history`, appending `note`, close resolutions, the descendant-close guard, `open`, all three `dep` verbs, JSON on four verbs, logical `plans:` refs, `doctor --fix-design-refs`, the pytest-store firewall, the ACE bead pane, and a skill rewrite (7 → ~17 verbs). Design-link resolution went 31% → 90%. Leaked fixtures purged.

**Two things stand out as new:**

1. **The one skipped recommendation was the keystone.** `bd/work_phase_bead` and `bd/next` still say "Do NOT create new beads" verbatim. So `--tier plan` usage is still exactly 3 beads, all closed — unchanged across 403 new beads. Every dependency it needed has now shipped; only the prohibition remains.

2. **A good fix quietly broke a command.** The 07-28 launch-preassignment change means beads sit in `open` for a median of **65 seconds** — just the compile→launch window. `sase bead ready` isn't empty because the backlog drained; it's empty because an `open` bead is one being launched right now. `#bd/next` can no longer select anything, and `docs/xprompt.md` still advertises it.

Other findings worth flagging: bead pages (2,419 published, `sase bead pages url`) are absent from both agent-facing docs; `sase bead onboard` now misstates where the store lives; event actor attribution is only 13–27%, which blocks the flow-metrics work; `doctor` misses 11 of 39 broken links including two live-regression cases; and `sase bead history --lost-notes` reports 301 recoverable beads with `--restore` never run.

The 11 ranked recommendations lead with the prompt edit, then the `open`/`ready` design decision, then the doc repairs — nothing in the top five crosses the Rust boundary. Upstream contributed 120 commits in the same window, almost entirely Dolt/server plumbing; the "don't follow" verdict holds, with five small transferable items cited.

One judgment call you may want to revisit: `BeadEditModal` (TUI title/description editing) shipped against both prior reports' explicit "no TUI CRUD" anti-recommendation. It's narrow and arguably fine — I ranked it last as a boundary to state deliberately rather than a thing to undo.

I made these changes — the research report is mine. Let me commit it.

Single untracked file — the two finalizer entries point at the same path. One commit covers both.

Convention is `docs(research):`. Writing the message file.

Committed and pushed.

**`bb3925c docs(research): re-measure bead improvements as of 2026-07-30`** — research repo is clean and in sync with `origin/main`.

The finalizer listed `research` twice (once as a linked repo, once as an SDD sidecar), but both entries point at the same path, so the single commit covered both. One note: the primary commit succeeded, but agent-hood publication was deferred because the agents sync lock was busy — it's queued and retries on its own, nothing to do.

The report itself is at `sase/repos/research/202607/sase_beads_improvements_20260730.md`: a re-measurement of the two prior bead reports against the live store, showing most of the 07-25 top-10 shipped in five days, and leading with two new findings — the skipped "don't create beads" prompt line that kept `--tier plan` frozen at 3 beads, and the 07-28 launch-preassignment change that left `sase bead ready` empty by construction. Ends with 11 ranked recommendations.
