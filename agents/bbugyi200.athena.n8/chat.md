# Chat History - ace-run (n8)

- **TIMESTAMP:** 2026-07-28 13:01:44 EDT
- **MODEL:** claude/opus
- **AGENT:** n8

## Prompt

#gh:gh_sase-org__sase I keep seeing the term SDD thrown around a lot, but that terminoligy should be completely replaced / removed at this point. Can you help me audit this codebase to determine everywhere that this term is used to give me an idea of how difficult it would be to remove/replace this term? Express your answer by setting some sase variables. %model:opus

## Response

I'll audit the codebase for SDD usage. Let me start by getting a broad picture.

Audit done. Variables are set on this run (agent `n8`).

## Scalars

| Variable | Value |
|---|---|
| `sdd_total_occurrences` | 8,412 (sase repo, temp dirs excluded) |
| `sdd_files_touched` | 637 |
| `sdd_src_files` | 254 (61 = the `src/sase/sdd/` package, 188 outside it across 24 subpackages) |
| `sdd_test_files` | 316 |
| `sdd_doc_files` | 45 |
| `sdd_paths_to_rename` | 133 |
| `sdd_python_identifiers` | 571 distinct |
| `sdd_import_refs` | 916 `sase.sdd` refs across 261 files |
| `sdd_core_files` / `sdd_core_occurrences` | 29 / 534 (in `sase-core`) |
| `sdd_env_vars` | 9 |
| `sdd_difficulty` | **high** |

Also set: `sdd_scope_summary`, `sdd_hard_surfaces`, `sdd_easy_surfaces`.

## The shape of it

Roughly 90% of the 8,412 hits are mechanical — `src/sase/sdd/` is a self-contained 61-module package with 36 exported names, and the blast radius outside it is concentrated in `ace` (54 files), `main` (21), `bead` (21), `axe` (15). A rename + import rewrite handles that.

The cost is in 9 spots that aren't sed-able:

- **`sdd/` as a real on-disk directory** — 519 path literals (`sdd/beads` 265, `sdd/plans` 256, plus research/prompts/tales/epics). Only applies to `in_tree` storage.
- **`.sase/sdd-store.json`** — persisted state, needs read-both/write-new.
- **`<owner>/<repo>--sdd`** sidecar naming (78 refs) — this renames actual remote GitHub repos.
- **9 `SASE_SDD_*` env vars** and the `sdd:` config block + `commits_toggle_sdd` keymap action.
- **12 persisted record/JSON fields** (`sdd_plan_path`, `sdd_base_sha`, `sdd_sidecar_suffix`, …).
- **8 `Sdd*Wire` types** crossing the Python↔Rust boundary — requires lockstep changes in `sase-core`.
- **Published doc URLs**: `docs/sdd.md`, `docs/sdd_storage.md`, `blog/posts/beads-and-sdd.md`.

Three findings make this cheaper than the raw count suggests:

1. The on-disk plan/artifact-link **syntax carries no `sdd` token** — `artifact_link.rs` only has it in error message text. No file-format migration for plans.
2. **Sidecar repos already store bare `plans/`, `beads/`, `research/`** with no `sdd/` prefix — your primary storage mode is already SDD-free on disk.
3. `sdd_kind_roots()` in `src/sase/sdd/_paths.py:82` **already falls back to bare `<kind>/`** alongside `sdd/<kind>/` — the in-tree compatibility hook you'd need for the directory rename exists today.

There is no `sase sdd` CLI subcommand, and SDD is already gone from the `AGENTS.md`/`CLAUDE.md` glossary — only 3 memory files still mention it.
