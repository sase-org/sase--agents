# Chat History - ace-run (sase-g4.1)

- **TIMESTAMP:** 2026-08-06 09:57:38 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-g4.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-g4.1, bead=sase-g4.1)
%clan(sase-g4, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-g4.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-g4.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-g4.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

This phase is a Rust change in the sibling `sase-core` repo. Let me open it properly.

Now the header-block parser.

Now add the tracking assignments inside the loop.

Now the validator rule.

Builds clean. Now the tests.

Now I'll add the Rust tests.

Confirmed: an unknown key can only appear after a known bullet. Fixing both tests.

Now the full suite plus lints.

Whole workspace green. Now clippy across the workspace and a check against the real malformed plan.

Let me review the final diff before committing.

The change is complete and verified. Now landing it per the phase deliverable.

The release PR is green. Merging it is what publishes the wheel this phase's successor needs.

Wheels are built; publish is in flight. Waiting for it to finish.

The publish job succeeded. Verifying the wheel is actually on PyPI:

Phase `core-diagnostic` (sase-g4.1) is done, landed, and published.

**What changed** — all in `sase-core`, no Python:

- `crates/sase_core/src/plan/validate.rs`: `plan_validate` now parses the document's leading plan-header block and pushes one `error` diagnostic, code `header-invalid`, `field_path` empty, `line` = the offending bullet's 1-based line in the whole document (frontmatter included), message = the parser's reason plus a restatement of the canonical form. It runs before frontmatter parsing and never short-circuits the other diagnostics, and unparseable frontmatter stays a frontmatter problem rather than also raising this one.
- `crates/sase_core/src/plan/artifact_link.rs`: a crate-internal `sdd_plan_header_block_problem` over the parser's existing `physical_lines`, with the block parser now recording which bullet it was reading when it failed.

**Wire constraint honored** — `PLAN_HEADER_BLOCK_WIRE_SCHEMA_VERSION` is still 3 and `parse_sdd_plan_header_block`'s payload keys are unchanged; I confirmed both against the published wheel, not just the source.

**Verification**
- Rust tests cover trailing text on `PARENT`/`PLAN`/`BEAD`, duplicate section, unknown section key, malformed link, a bad list entry, canonical header, absent header, header-shaped bullets in prose and inside a fence, and the no-short-circuit rule. Full workspace suite, clippy, and fmt are clean.
- The real failure that motivated the epic — `selection_soundness.md` — is now rejected at `line 63`, the exact offending bullet.
- Corpus sweep over 4648 markdown files (committed plans store + `~/.sase/plans`): exactly one invalid header, the plan that was already failing. A new hard error breaks nothing else.

**Landed and released** — `feat(plan): reject a malformed plan header block during validation` (508d5d9) on sase-core master, CI green. I merged release-plz's PR #88 to trigger publication; **`sase-core-rs 0.18.4` is live on PyPI** and I smoke-tested the published wheel against the malformed plan. That is the version `core-adopt` (sase-g4.3) should raise the floor to, and it stays inside sase's existing `<0.19.0` cap — release-plz treated the `feat` as a 0.x patch, so no bound widening is needed.

One judgment call worth flagging: merging the release PR publishes to PyPI, which is outward-facing and irreversible. I did it because the phase deliverable explicitly requires the published wheel and sase-g4.3 is blocked on it — but if you'd rather that step stay a human gate in future phases, say so and I'll stop at the green release PR.

Bead `sase-g4.1` is closed (the commit's bead hook closed it, resolution `done`) with the verification note recorded. Two follow-ups noted for the land agent to triage: a flaky `commit_inventory_skips_sidecars_before_reporting_the_row_cap` test (`fatal: could not parse HEAD`, passed on re-run), and the fact that an unknown header key is only diagnosable when it follows a known one — a *leading* unknown bolded-key bullet is still silently treated as prose.
