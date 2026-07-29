# Chat History - ace-run (research.p.final)

- **TIMESTAMP:** 2026-07-29 07:22:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.p.final
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_065513.md`

## Prompt

%id(final, clan=research.@) %wait(priority=20) %m:@research_lead %wait:research.p.cdx %wait:research.p.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I'm looking for new and improved ways that users can view, copy, and reference sase artifacts (for example, from the `Artifacts` panel in the TUI). Can you do some research to help me decide the best path forward? End your analysis with a ranked list of recommended improvements.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.@.cdx` -> `__a`, `research.@.cld`
   -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory (do NOT end the name with
   `_consolidated` or `_<YYYYmmdd>` or anything similar unless it relates to the research topic), create
   `<month-dir>/<name>/`, and move the two reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files
   and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings from both reports and your own
   research, resolve conflicts, cut duplication, and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both transcripts to identify which report each researcher wrote.

Both reports are read. Report A = codex (`sase_artifact_view_copy_reference_research.md`), Report B = claude (`artifact_view_copy_reference_20260729.md`). Now let me verify their competing claims against the actual code.

This is decisive. Let me investigate why the artifact graph was removed — this bears directly on the central disagreement between the two reports.

All claims verified. Now writing the consolidated report.

Done. Final layout:

```
sase/repos/research/202607/artifact_refs_and_inspector/
├── artifact_refs_and_inspector__a.md   (codex — was sase_artifact_view_copy_reference_research.md)
├── artifact_refs_and_inspector__b.md   (claude — was artifact_view_copy_reference_20260729.md)
└── artifact_refs_and_inspector.md      (consolidated)
```

Both originals preserved via `git mv` (staged as renames); nothing committed.

## What the merge changed

The two reports agreed on the diagnosis — *an artifact in SASE is a path, and a path is not a durable name* — but split on the fix. Report A wanted a new artifact registry in `sase-core` with a `sase://` URI scheme; Report B wanted to generalize the `plans:` resolver already in the Rust core. Five findings from my verification pass settle it:

1. **SASE already built A's registry and deleted it.** The unified artifact graph — SQLite store, SQL-backed search, paged detail, seven ingestion sources, graph export — landed 2026-05-05 and was removed 2026-05-06 in `b455124`: **12,898 deletions**, ~24 hours alive, never shipped. A cites this commit to warn against rebuilding a graph, but its own proposal overlaps much of what was deleted.

2. **SASE also solved this exact problem correctly two days ago.** Epic `sase-9z` closed 2026-07-27 with a five-phase playbook (core scheme → route all resolvers → persist → show ref + resolved path → doctor/repair) and **repaired 227 stored links that no longer resolved**. That's a reusable template, and it drops B's "L, keystone" sizing — `plans:` refs are already bound into Python.

3. **B's "the field is clear" is wrong at the core level.** One open bead in the Python repo, yes — but `artifact_link.rs` (62 KB) landed 07-21, `refs.rs` 07-27, and three header-block commits 07-28. New reference work should sequence *with* `sase-ag`/`sase-ai`, not beside it.

4. **Path rot is measurable now: 31% of artifact `source_path` values (1,225/3,985) are already dead**, while 100% of stored paths survive. Worse, `Y` falls through to the `source_path` branch and emits a **bare relative path with no workspace anchor** into recycled `sase_<N>` checkouts — so it's often silently *wrong*, not merely broken. Both reports understated this.

5. **The registry gap is three fields, not a store.** `artifact_file_id` = `sha256(project|workflow|timestamp|dir|path|label)[:24]` — location-derived (A correct) but the index already carries 9 of ~14 proposed fields. Missing only `sha256`, `size_bytes`, `mime_type` — and the full SHA-256 is *already computed and discarded* for explicit artifacts.

Also corrected: A's `cat` safety claim is real but narrower (the `bat` branch already has `--` hygiene and refuses binaries; exposure is precisely "`bat` absent"), and neither report caught that `copy_to_system_clipboard` is subprocess-only — with Textual pinned at 8.0.1, **every copy in ACE silently fails over SSH without a local clipboard binary.**

## Ranked list (9 items, consolidated)

1. **Tranche zero** — four small independent fixes: restore `%`/`m` on 4 gated sub-tabs (confirmed defect, `%s` doesn't respond), fix `Y` to prefer the stored path, replace raw `cat`, surface `research` in Plans (2 lines)
2. **Extend `plans:` into a kind-tagged artifact ref** in `sase-core`, reusing the `sase-9z` five-phase shape — keystone
3. **`sase artifact` read CLI** + the three missing record fields
4. **Make `PreviewPanelModal` a real reader** (it has *only* scroll and close today)
5. **Files sub-tab** to reach the rich viewer from the panel
6. **"Copy as…" palette**, with Textual OSC 52 as first transport
7. Marks/bulk actions · 8. Prompt-bar refs (the payoff for #2) · 9. Vocabulary, footer, Jump All

I only read the sase workspace checkout — no source changes, so `just check` doesn't apply.

I made these changes in this session, so I'll commit them. Let me invoke the commit skill.

I'll record the skill usage and inspect the changes.

The old paths no longer exist on disk (renames already staged). Retrying with just the new paths.

Committed and verified clean.

**Commit `0fdc0c7`** in the research sidecar repo — `docs(research): consolidate artifact view, copy, and reference research`:

- Both researcher reports moved into `202607/artifact_refs_and_inspector/` as `__a.md` (codex) and `__b.md` (claude), recorded as pure renames with **0 content changes** — originals preserved exactly.
- Consolidated report added at `artifact_refs_and_inspector.md` (481 lines).

`git status --short --branch` shows `main...origin/main` with no ahead/behind markers — working tree clean and pushed.

The initial commit attempt failed because I passed the pre-rename paths alongside the post-rename ones; since the renames were already staged, those pathspecs no longer matched anything on disk. Re-running with only the three current paths succeeded, and git detected the renames on its own.

No changes were made in the sase workspace checkout itself (research only), so `just check` doesn't apply.
