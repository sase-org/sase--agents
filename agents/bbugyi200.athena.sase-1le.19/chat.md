# Chat History - ace-run (sase-1le.19)

- **TIMESTAMP:** 2026-10-15 23:24:41 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1le.19

## Prompt

#gh:gh_sase-org__sase
%id(19, clan=sase-1le, bead=sase-1le.19)
%model:@medium
%auto
%w(sase-1le.12,sase-1le.13,sase-1le.3,sase-1le.9, for_epic=false)
%w(bead=sase-1le.12)
%w(bead=sase-1le.13)
%w(bead=sase-1le.3)
%w(bead=sase-1le.9)
Can you complete the work for bead sase-1le.19? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1le.19 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1le.19 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1le.19`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1le.19 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1le.19 is done and closed.

The homepage is now one screen: a two-column hero with the "Run a team of coding agents. Keep every change reviewable." headline, the documented install floor, a three-line copyable install block, one primary CTA (Run your first agent) plus the How SASE works secondary, and the fanout mp4 demo with poster, controls, and no autoplay. Below are four capability cards pointing at Concept pages, the four Learn/Do/Understand/Look-up doors, and a footer row (launch essay, blog, handbook PDF, acknowledgements). The old role cards, primitives list, and next-click grid are gone, with the orphaned CSS trimmed from both stylesheets.

Also landed: README's front door rewritten around the four doors plus four key guides; TUI onboarding links and the sudo docs URL retargeted to the most specific Concept pages with tests updated; and the observed-reader testing kit at [reader-testing](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/docs/contribute/reader-testing.md), wired into the nav and Contribute hub.

Verified before closing: docs contract lint passes, the URL contract is green across 285 URLs, onboarding tests pass 20/20, mypy is clean, and Playwright screenshots confirmed install plus demo above the fold at 1280×800 with a working mobile drawer at 390px. Two failures reproduce identically on the clean tree and were recorded as follow-ups instead of blocking: the renderer/prettier drift that fails `fmt-docs-check` (which also visibly breaks glossary tooltips site-wide), and stale `getting_started` links in three Concept pages that trip the strict build. The docs word ceiling ratcheted from 922 to 361 on its own.
