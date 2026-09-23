# Chat History - ace-run (sase-16n.10)

- **TIMESTAMP:** 2026-09-23 08:14:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.10

## Prompt

#gh:gh_sase-org__sase
%id(10, clan=sase-16n, bead=sase-16n.10)
%model:@medium
%auto
%w:sase-16n.2,sase-16n.5,sase-16n.7,sase-16n.8,sase-16n.9
%w(bead=sase-16n.2)
%w(bead=sase-16n.5)
%w(bead=sase-16n.7)
%w(bead=sase-16n.8)
%w(bead=sase-16n.9)
Can you complete the work for bead sase-16n.10? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.10 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.10 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.10`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.10 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.10 is done and closed.

What changed: guides, `sase run` help, and the `sase_run` skill now present `+<project>` tags as the default project spelling, keeping `#gh:`/`#git:` for Patches, `owner/repo`, `@agent`, and new projects. Added the glossary Project Tag strand, updated the sase-project and xprompts memory notes, republished memory, and removed the redundant `gh_dotfiles`/`gh_sase` chezmoi shortcuts.

Verified: `sase doctor project.name_collisions` is clean, `sase project list` shows the TAG column, `+sase`/`+Sase`/`+home` expand to their canonical refs, anchored `+ssae` raises with suggestions, `sase tool run check` is green, and no epic symbols remain. Two notes: `sase.schema.json` was intentionally untouched (its `#gh:` text covers namespace completion, which stays), and the `sase xprompt expand` CLI dry run was blocked by a sibling's live claim on workspace 18, so expansion was verified at the function level instead. Final declaration accepted for both repos (host commits).
