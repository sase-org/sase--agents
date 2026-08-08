# Chat History - ace-run (sase-hb.3)

- **TIMESTAMP:** 2026-08-08 01:52:52 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-hb.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-hb, bead=sase-hb.3)
%model:@medium_phase_worker
%auto
%w:sase-hb.2
%w(bead=sase-hb.2)
Can you complete the work for bead sase-hb.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-hb.3 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-hb.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Starting with the plumb-through work.

Now `sase xprompt show`.

Now the show rendering — chip plus a `slash` detail row.

Now the catalog HTML badge and completion row.

Now add a render test for the split names.

Now tests for the mobile bridge, list JSON, and completion rows.

Now the `sase xprompt list` JSON test.

Now the completion-row test.

Now add a row-rendering test asserting both forms share the same source definition and cross-name display.

Now the shared skill-destination module.

Now the writer guard in `save.py`.

Now the save modal's destination list.

Now wire the row fields and modal display.

Now the modal verdict text and the caller passing `skill=`.

Now the caller passes `skill=`.

Now update the two save round-trip tests.

Now a test for the skill destination index and modal verdict.

Now a test for the destination index itself.

I'll add an action-level test that skill drafts request skill destinations, plus a unit test for the index.

Now a unit test for the destination index itself.

Now the docs.

Rewriting the Skill Field section for the cutover.

Now the ToC and content_layout/editor/ace docs.

Now editor.md, ace.md, and development/architecture path references.

Now docs/init.md skill wording, and the CLI help strings.

Now the CLI help strings for `sase skill`.

Now give `SkillPlacementError` a real consumer in the ACE save path.

Now `SkillDestination` gets a real consumer via a row helper.

Lint is clean. Now the full suite.

Bead `sase-hb.3` is done and closed.

**What shipped**

*Catalog and read surfaces* — `skill_name` now flows through the mobile/editor helper catalog payload (filling the field the `sase_gateway` contract already documented), `sase xprompt list` JSON, the `sase xprompt show` record (a `slash` row and a `skill · /<name>` chip alongside the `#skills/<name>` reference), the HTML catalog badge, and completion rows, where a `#skills/foo` row advertises `/foo`. Both reference forms resolve to the same `XPromptAssistEntry`, so argument hints, previews, and jumps agree — that part was already true after Phase 2, and it now has a test pinning it.

*Authoring* — new `src/sase/xprompt/skill_locations.py` is the single source of canonical skill destinations. A draft declaring `skill:` is offered only `sase/skills/` scopes; the save modal's verdict reads `#<project>/skills/foo · /foo` rather than implying `#foo`; and `save_markdown_xprompt`, `save_markdown_document`, and `save_config_xprompt` raise `SkillPlacementError` (shown verbatim in ACE) instead of writing a skill into `sase/xprompts/` or a config entry.

*Docs* — rewrote the xprompt.md Skill Field section with a canonical-sources table, the source/reference/provider name split, and the hard-cutover statement; added a Skill Order section to content_layout.md; updated the discovery-order note, architecture/development path tables, ace.md, editor.md, init.md, and the `sase skill init` help strings.

**Verification** — `just fmt`/`just lint` clean (symvision included), `just test` 27602 passed / 10 skipped, `just test-visual` 562 passed / 1 skipped.

**One thing to know:** `just check-full` stops at its `sase validate` gate because `~/sase/xprompts/bob_query.md` still declares `skill:` outside a canonical source. That is the chezmoi source migration the plan assigns to sase-hb.4 (currently in progress), not a Phase 3 regression — every other gate passes. I also left a `PROPOSED FOLLOW-UP` note: `sase/memory/generated_skills.md` still documents the old `src/sase/xprompts/skills/` path, and fixing it needs a memory edit plus `sase memory init`, which requires your explicit permission.

Bead already closed and published. Now committing.

Done. Working tree clean, branch level with `origin/master`.

**Bead** — `sase-hb.3` was already closed and published; the re-run confirmed it (`Already closed … done`) with no unpublished-close diagnostic, and appended the verification note.

**Commit** — `feat(skills)!: surface skill names across read surfaces and restrict authoring to skills/`, covering all 31 listed files (including the two new ones, `src/sase/xprompt/skill_locations.py` and `tests/xprompt/test_skill_locations.py`). Marked breaking because saving an xprompt that declares `skill:` outside `sase/skills/` now raises `SkillPlacementError`.

Verification carried over from the work pass: `just fmt`/`just lint` clean, `just test` 27602 passed / 10 skipped, `just test-visual` 562 passed / 1 skipped. `just check-full` still stops at its `sase validate` gate because `~/sase/xprompts/bob_query.md` declares `skill:` outside a canonical source — that's the chezmoi source migration assigned to sase-hb.4, not a Phase 3 regression.
