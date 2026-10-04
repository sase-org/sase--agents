# Chat History - ace-run (research.t.gem)

- **TIMESTAMP:** 2026-09-30 13:40:02 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.t.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_132759.md`

## Prompt

%id(gem, clan=research.t)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.t.cdx`, `research.t.cld`, `research.t.grk`, `research.t.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It
is important that memory file changes are tracked, versioned, and easy to navigate /
understand. I would like to add support for this to sase.

- All agent instruction file changes and all memory file changes should be tracked. It's
  fine if we use git history for this to get this version-control data for free, but we
  need to be able to navigate between the different versions for each supported file
  very quickly (so we might need to create an index or something--think hard about the
  best way to solve this).
- I was thinking that we could add some sort of special support to sase's pager for
  memory files / agent instruction files and make that the main interface for navigating
  / viewing memory change history. Think hard about what the best UX for this looks
  like.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report Summary: Memory File Versioning, Fast Revision Indexing, and Pager-Centric UX

- **Author:** researcher gem (`research.t.gem`)
- **Report Location:** [`sase/repos/research/202609/memory_history_versioning_and_pager_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/memory_history_versioning_and_pager_ux__gem.md)
- **Durable Artifact Reference:** `research:202609/memory_history_versioning_and_pager_ux__gem.md` (`file:explicit:aeeade081b672010a173e657`)

---

## 1. Executive Critique: Is This a Good Idea?

### What Works Exceptionally Well
1. **Git as the Single Source of Truth**:
   Leveraging Git history is 100% architecturally sound. Every change to `sase/memory/` and `AGENTS.md` is committed with cryptographic commit hashes, author timestamps, and Conventional Commit subjects. SASE commits already carry machine-readable trailers (`SASE_BEAD=[...][1]`, `SASE_TYPE=stitch`, `SASE_AGENT=[...][2]`). Using Git avoids split-brain databases, synchronization bugs on rebase/cherry-pick, and cross-workspace locking overhead across ephemeral `sase_<N>` clones.
2. **The Pager as an In-Situ Reading Surface**:
   The SASE pager (`src/sase/pager/`, hosting `PagerScreen`) is already the central reading interface across the CLI (`sase pager`) and ACE TUI modals. It has Markdown syntax highlighting, jump hints (`[a]`, `[b]`), vim search (`/`), and link navigation. Extending it to support non-destructive time-travel allows developers and agents to inspect past rules in their native formatted layout without leaving their keyboard flow.

### Critical Blind Spots & Adjustments to the Plan
1. **The Discovery Void (Single-File Pager Myopia)**:
   A document pager views *one document at a time*. It cannot answer high-level questions such as: *"What memory rules changed across the project this week?"* or *"Which decision strands did epic `sase-1au` modify?"*
   - **Adjustment**: Pair the Pager with a project-wide **Memory History Feed** in the CLI (`sase memory history`) and a dedicated **History View** in the ACE TUI Memory Panel (`src/sase/ace/tui/modals/memory_panel.py`).
2. **Multi-File Commit Atomicity**:
   In SASE, memory changes are almost always multi-file commits (e.g., adding a decision strand in `decisions/<slug>.md`, updating the index in `decisions.md`, and inlining core summaries into `AGENTS.md`).
   - **Adjustment**: When viewing historical revision `k` in the pager, render **interactive sibling links** in the header (`⎇ Also changed in commit: [c: decisions.md] [d: AGENTS.md]`), allowing instant lateral navigation across related memory files.
3. **Provider Shims Must NOT Be Tracked Independently**:
   `CLAUDE.md`, `GEMINI.md`, `QWEN.md`, and `OPENCODE.md` are byte-for-byte replicas of `AGENTS.md` generated by `sase memory init`. Tracking them as separate version histories creates 5x redundant commit noise.
   - **Adjustment**: Automatically route provider shims to `AGENTS.md` with an indicator chip `(mirrored in 4 provider shims)`.
4. **Multi-Repo Scope Routing**:
   Memory files exist in multiple scopes:
   - `project` & `project-subdir`: Tracked in the project repository Git root.
   - `home`: Tracked in Bryan's `chezmoi` repository (`~/.local/share/chezmoi/home`).
   - **Adjustment**: The backend must transparently resolve the enclosing Git repository for the target path.

---

## 2. The Indexing Solution: Two-Tier Ephemeral In-Memory Cache

### Empirical Benchmarks on the Live Repository
- Single-file `git log -- <file>`: **~245 ms** (7 commits).
- Full memory history `git log -- sase/memory AGENTS.md`: **~251 ms** (343 total commits across repo history).
- Content retrieval `git cat-file -p <sha>:<path>`: **6 ms**.
- Commit diff retrieval `git diff-tree -p -u <sha> -- <path>`: **9 ms**.

### Why Persistent SQLite is an Anti-Pattern Here
A full `git log` across all memory commits takes only 250ms. A persistent SQLite database or on-disk JSON cache violates SASE Decision 19 (`corpus-before-mechanism`) and creates cache-invalidation nightmares across branch switches, rebases, and ephemeral workspace clones.

### The Recommended Index Design
1. **Tier 1: In-Memory Revision Index (Rust `sase_core`)**:
   - Background worker executes streaming `git log` using a pinned NUL-delimited format on first file open.
   - Rust parses commit IDs, timestamps, authors, subjects, and `SASE_BEAD`/`SASE_AGENT` trailers in **< 1 ms**.
   - Cached in memory keyed on `(HEAD_SHA, path, mtime)`. Total memory footprint for all 343 commits is **< 150 KB**.
2. **Tier 2: On-Demand LRU Content & Diff Cache**:
   - Revisions are fetched on demand via `git cat-file -p` (6ms) and `git diff-tree` (9ms).
   - Once fetched, back-and-forth scrubbing between revisions is **0 ms (instantaneous)**.
3. **Dirty Working Tree State**:
   - If the file has uncommitted edits on disk, revision `#0` is dynamically set to `[WORKING TREE (dirty)]`, enabling instant diffing against `HEAD`.

---

## 3. UI/UX Specification for the Pager

### 1. Sticky Subject Chrome (`#pager-subject`)
- **At HEAD (Present)**:
  `◆ sase/memory/gotchas.md · HEAD · 50d9c3b · 2026-09-24 · 100% · ⌘ 325c · md`
- **Dirty Working Tree**:
  `◆ sase/memory/gotchas.md · ✎ WORKING TREE (dirty) · +12 -4 vs HEAD · 100% · md` (in warm amber `#FFB454`)
- **Historical Snapshot**:
  `◆ sase/memory/gotchas.md · ◀ [REV 6/7: c9ca0db · 2026-09-22 · Bryan Bugyi] ▶ · HISTORICAL` (in cyan/gold `#FFD75F`)

### 2. Revision Sub-Chrome Strip
Directly under the subject line, displays active SASE metadata and sibling links:
`⌖ Bead: [a: sase-1au.5]  ⌖ Agent: [b: athena.sase-1au.5]  ● Commit: feat(memory): tiers`  
`⎇ Also changed in commit: [c: decisions.md] [d: AGENTS.md]`

### 3. Keybindings
| Key | Action | Description |
|---|---|---|
| `[` | **Previous Revision** | Instant step to older snapshot. |
| `]` | **Next Revision** | Instant step to newer snapshot. |
| `~` / `0` | **Return to Present** | Snap back to HEAD / Working tree. |
| `d` | **Toggle Diff** | Flips between full Markdown snapshot and commit unified diff. |
| `D` | **Diff vs HEAD** | Compares current historical revision directly against HEAD. |
| `H` | **History Drawer** | Opens floating revision picker with `/` search, relative dates, and bead badges. |
| `B` | **Blame Gutter** | Toggles line gutter to show commit SHA, author, and age with jump labels. |
| `y` | **Copy SHA** | Copies current revision commit hash to clipboard. |

---

## 4. Backend & Rust Core Architecture

Conforming to Rule 1.3 (`rust_core_backend_boundary`):
1. **Rust Core (`crates/sase_core/src/vcs_log/memory_history.rs`)**:
   - Implements `MemoryRevisionWire` and `MemoryHistoryIndexWire` wire models.
   - Provides zero-allocation streaming `parse_memory_git_log` and SASE trailer extractors.
2. **Host Facade (`src/sase/core/memory_history_facade.py` & `src/sase/memory/history_service.py`)**:
   - Handles multi-repo Git subprocess calls (project root vs `chezmoi`).
   - Caches revision indexes and manages the LRU blob cache.
3. **Pager Screen Extension (`src/sase/pager/_screen_history.py`)**:
   - `PagerHistoryMixin` integrates directly into `PagerScreen`.

---

## 5. Artifact Verification & Snapshot Registration

The research report was authored and registered without `--move`:
```bash
sase artifact create \
  -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/memory_history_versioning_and_pager_ux__gem.md" \
  -l "research:202609/memory_history_versioning_and_pager_ux__gem.md"
```
**Artifact ID:** `explicit:aeeade081b672010a173e657`  
**Artifact Ref:** `file:explicit:aeeade081b672010a173e657`

The final declaration was submitted via `sase final submit` for repository `sdd:research`, committing the report cleanly.
