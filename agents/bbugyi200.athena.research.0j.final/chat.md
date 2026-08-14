# Chat History - ace-run (research.0j.final)

- **TIMESTAMP:** 2026-08-14 16:12:11 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0j.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_153112.md`

## Prompt

%id(final, clan=research.0j) %wait(priority=20) %m:@research_lead
%wait:research.0j.cdx %wait:research.0j.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to unify the different Artifacts tabs with the goal of
using an API / contract of some sort to allow specific sidecar/artifact repos to specify
how their corresponding tabs behave. This will also make adding new functionality more
rewarding in the future (if we get the abstraction right), since all custom sidecar
repos (even ones that are configured for other users that we don't know about) get new
functionality for the cost of a single implementation.

- See the artifacts_pane_contract.md file in the research sidecar repo for related
  research / inspiration (keep in mind this file is a bit dated since some of the
  requirements this agent was given were not quite right/complete and I ran this agent a
  few days ago--related changes have been made since then).
- I do want the "Patch" sub-tab to be included in this unification, with the goal of
  migrating this tab over to the same look and feel as the other sub-tabs.
- Before we do this, however, I would like to figure out how to generalize some of the
  "Patch" tab's coolest features (powerful search syntax, saved queries,
  ancestors/children jumpers, etc...) so they can be included in the contract.

Can you do some reasearch to help me decide the best way to implement this based on the
requirements and notes listed above?

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0j.cdx` -> `__a`, `research.0j.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both transcripts to identify which report each researcher wrote.

Both transcripts identified. Now let me open the research sidecar repo properly.

Both reports are read. Now let me verify the contested claims myself — the central disagreement is *where the query engine lives* (Rust-first vs Python-first).

This is decisive — the Patch query parser is **already in Rust**. Let me verify what's hard-coded there.

I have enough verified evidence. Let me set up the directory and move the reports.

Verification complete. Writing the consolidated report.

Let me re-verify one claim in the report — the bead list query returned suspiciously empty.

Consolidated report written. Both source reports preserved and moved; all cross-links resolve.

**`sase/repos/research/202608/artifacts_query_and_pane_contract/`**
- `artifacts_query_and_pane_contract__a.md` (cdx, 847 lines)
- `artifacts_query_and_pane_contract__b.md` (cld, 858 lines)
- `artifacts_query_and_pane_contract.md` (consolidated, 703 lines)

## What the two researchers agreed on

Independently, both landed on the same architecture: **one behavioral contract with multiple adapters**, Patch as the richest built-in adapter rather than an exception, providers declaring *facts* not UI code, relations as typed directed edges, and saved queries migrated to pane-scoped storage. Two independent passes converging is the strongest signal in the report — treat that core as settled.

## Three corrections my pass makes

**1. The Patch query parser is already in Rust.** `sase/core/query_facade.py:33` calls `sase_core_rs.parse_query`; `crates/sase_core/src/query/` is 3,428 lines with a parity test already in place. So `__a`'s "move it to core" describes half-done work, and `__b`'s "build a new Python engine, lift later" would *fork a Rust engine back into Python* and guarantee an interim two-engine state. The real job is de-Patch-ifying what's there — a `VALID_PROPERTY_KEYS` allowlist, three inline sigil emissions, and `QueryCorpus` typed to `ChangeSpecWire`.

The reconciliation that satisfies both: pass the compiled query profile as a **call argument, not a persisted wire**. A per-call argument freezes no schema, which is the valid kernel of `__b`'s objection, while keeping `__a`'s destination.

**2. No `schema_version` bump is needed.** `__b` quoted `provider_spec.rs:18-25` correctly, then over-read it — the constraint binds the *version integer*, not additive fields. Verified there's no `deny_unknown_fields` on that wire, so optional additive fields are free at v1 today; that's exactly how `icon` shipped. (`__a`'s "accept v1 and v2" rollout doesn't work as written — the rejector is the *floor* core, so a new core accepting both changes nothing.)

**3. Capabilities must be derived, not declared.** `__a` is right, `__b`'s "safe capability subset" in provider YAML is wrong, and this is the decision that determines whether your actual goal is met: derivation is what makes a future host feature light up in a sidecar written before that feature existed.

## Sequencing conflict, resolved

`__a` says migrate Patch first (it's the stress test); `__b` says migrate it last (proven engine, cheapest rollback). Both are right about different things: **design against Patch from Phase 0** — freeze golden fixtures from its current behavior so the profile shape is honest — **then cut it over last**.

## Things I found that neither did

- The research sidecar **already encodes a family relation in filenames** (`__a`/`__b`/consolidated — this bundle is one). It's structurally identical to Patch's `__<N>` siblings and makes an ideal first *non-Patch* relation conformance case, needing no schema change.
- The real provider declares `status` as `type: string`, not `enum` — so "`ref.properties` becomes queryable free" is true but oversells quality; a four-character sidecar edit is the cheapest end-to-end proof of the whole thesis.
- Precise counts: **13 files / 26 `ref:`-dispatch sites** (`__a` said 12 files, `__b` said 13 sites).
- Bead `sase-lm` is a recorded live instance of a wire bump landing ahead of its floor — the failure mode §2.2 manages isn't hypothetical.

I verified `__b`'s defect inventory independently (accent collision/drift/global leak, the `o` double-booking, `entry_navigator` raising for Patches, the `FilterBar` class-var schema, `FileFilterBar`'s missing `NEGATABLE_KEYS`, `agent_query` as a self-declared fork). All hold. `sase-m5` is filed and is the only artifacts-related bead in flight — I didn't file duplicates, since the Phase 0 defects are already carried by the recommended plan.

All three files are in place. Committing now.

Committed and pushed — working tree clean, in sync with `origin/main`.

## Commit

`1f396a0 docs(research): consolidate the artifacts query and pane contract reports`

Both finalizer entries pointed at the same path (the research repo is listed as both a linked repo and an SDD sidecar), so a single commit covers both. `git status --short --branch` shows `## main...origin/main` with no ahead/behind — the push landed.

## What was committed

`sase/repos/research/202608/artifacts_query_and_pane_contract/`

| File | Source | Size |
| --- | --- | --- |
| `artifacts_query_and_pane_contract__a.md` | cdx researcher | 37k |
| `artifacts_query_and_pane_contract__b.md` | cld researcher | 52k |
| `artifacts_query_and_pane_contract.md` | consolidated | 46k |

Both source reports moved as git renames (history preserved), plus one content edit: `__b`'s cross-link to the earlier `artifacts_pane_contract.md` needed `../` after the move into the bundle directory.

The commit message records the merged architecture both researchers reached independently, and the three conflicts my pass resolved — the Patch query parser already being in Rust, no `schema_version` bump being required, and capabilities needing to be derived rather than provider-declared.
