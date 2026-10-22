# Chat History - ace-run (research.2n.gem)

- **TIMESTAMP:** 2026-09-26 14:06:03 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2n.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_135408.md`

## Prompt

%id(gem, clan=research.2n)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2n.cdx`, `research.2n.grk`, `research.2n.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to merge the
prompt stash panel with the prompt history panel using sub-tabs on that new, merged
panel.

- Also, I want to add a new, third sub-tab to this panel that contains archived/trashed
  prompts (aka the "stash trash"--this term should be added to the glossary as well as
  "prompt stash" and its alias, "stash") that the user deleted with the `d` keymap on
  the new sub-tab that the prompt stash panel is migrated to.
- We should start moving deleted prompts to this tab instead of deleting them entirely.
- We should only store up to the last `<N>` deleted prompts on this tab (then they
  should actually be deleted).
- `<N>` should be configurable via a new sase config field but should default to 20.
- Appropriate keymaps should be added to this new sub-tab that holds the stash trash.
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

# Research & Design: Unified Prompts Hub (Stash, Trash, History)

- **Researcher**: `research.2n.gem` (Swarm Member)
- **Report File**: [`unified_prompt_hub_and_stash_trash_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/unified_prompt_hub_and_stash_trash_design__gem.md)
- **Durable Snapshot**: `research:202609/unified_prompt_hub_and_stash_trash_design__gem.md` (`file:explicit:1909487c1cd6e200b5b69a24`)

---

## 1. Executive Summary & Verdict

The proposal to merge the **Prompt Stash** panel and **Prompt History** panel into a unified sub-tabbed modal with an added **Stash Trash** sub-tab is a **compelling and highly justified design improvement**.

### Key Findings
1. **Unification Clarifies User Mental Models**: Currently, users must remember two disjoint modal workflows: `@` / `,@` for Stash and `Ctrl+K` for History. Unifying them into a single **Prompts Hub** (`PromptsModal`) eliminates fragmentation and leverages SASE's standard [`PanelTabStrip`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/panel_tab_strip.py#L33-L70).
2. **Sub-Tab Semantic Separation**: While visually unified, each sub-tab serves a distinct operational purpose:
   - **Stash**: Interactive draft pad and reusable templates (mutable, restore & pop).
   - **Trash**: Bounded recovery and undo buffer for discarded drafts (FIFO pruning).
   - **History**: Immutable chronological journal of executed and cancelled runs (search, inspect, replay).
3. **Dedicated Trash Storage**: Stash trash must be stored in a dedicated, isolated file (`~/.sase/prompt_stash_trash.jsonl`) rather than via in-band soft-delete flags in `prompt_stash.jsonl`. This avoids wire-schema churn and lock contention with active stash reads.
4. **Rust Core Boundary (Rule 1.3 Compliance)**: Atomic mutations, multi-process file locking, FIFO truncation to `<N>` entries, and moving entries between stash and trash belong in `crates/sase_core/src/prompt_stash/` in the linked `sase-core` repository.
5. **Configurable Retention**: `<N>` is configured under `ace.prompt_stash.trash_limit` (defaulting to `20`), with `0` cleanly disabling retention (immediate permanent deletion).

---

## 2. Critique of the Proposal & Recommended Adjustments

### Is this a good idea?
**Yes.** In modern interactive developer environments, prompt drafting is iterative. The biggest vulnerability of the current Prompt Stash is that pressing `d` triggers an immediate, unrecoverable `pop_prompt_stash` delete on disk. Providing a safety buffer ("Stash Trash") solves this data-loss risk.

### Adjustments to the Initial Requirements
1. **Strict Scoping of Trash to Stash**:
   - The trash buffer must strictly apply to **Stash items**, not History. Prompt History entries are already immutable logs stored across monthly shards (`~/.sase/prompt_history/`). Deleting historical audit records is a maintenance operation (`sase prompt prune`), not a workspace draft action.
2. **Lazy Mounting & Asynchronous Loading**:
   - `PromptHistoryModal` streams records off-thread and builds a project catalog. If History loaded eagerly every time a user pressed `@` to restore a stash, TUI response time would suffer.
   - *Adjustment*: History must load **lazily**, only when the user switches to the History sub-tab (or when opened directly via `Ctrl+K`).
3. **Preserving Muscle Memory for Entry Points**:
   - Existing shortcuts should open directly to their corresponding sub-tab:
     - `@`, `,@`, `Ctrl+G p`, or clicking the top-bar `stash: ≡ N` indicator $\rightarrow$ Opens **Stash** tab.
     - `Ctrl+K` from the prompt bar $\rightarrow$ Opens **History** tab.
     - Global cycling inside the modal uses `[` and `]` (standard SASE sub-tab navigation).

---

## 3. Sub-Tab Architecture & Keymaps

### 3.1 Sub-Tab Ordering & Accents
$$\mathbf{[ \text{ 1. Stash (N) } \mid \text{ 2. Trash (M/20) } \mid \text{ 3. History } ]}$$

- **Stash**: `#FF87D7` (orchid-pink) — matches the top-bar indicator badge.
- **Trash**: `#E5C07B` (warm amber) — communicates a recovery zone without harsh error reds.
- **History**: `#61AFEF` (sky blue) — matches SASE info/audit surfaces.

### 3.2 Keymap Specification

#### Global Modal Controls
- `[` / `]`: Cycle sub-tabs (`Stash` $\rightleftarrows$ `Trash` $\rightleftarrows$ `History`).
- `Esc` / `q`: Dismiss modal.
- `Ctrl+D` / `Ctrl+U`: Scroll preview pane half-page down/up.

#### Sub-Tab 1: Stash (`stash`)
- `1`-`9`, `0`: Instant restore numbered row to prompt bar and pop (or keep if pinned).
- `tab`: Toggle restore mark (`✓`).
- `space`: Toggle persistent pin (`📌`).
- `a`: Select/deselect all.
- `d`: Mark row to move to Trash (`✗`).
- `D`: Mark all rows to move to Trash.
- `enter`: Apply pending actions (moves marked deletes to Trash; restores marked pops to prompt bar).

#### Sub-Tab 2: Stash Trash (`trash`)
- `enter`: **Restore to Prompt Bar** (loads highlighted/selected trashed prompt directly into prompt bar and removes it from trash).
- `u`: **Untrash / Put Back** (moves row back into active Stash without mounting in the prompt bar).
- `U`: **Untrash All** (moves all trashed items back into active Stash).
- `d`: **Purge Row** (marks row for permanent deletion from disk).
- `D` or `X`: **Empty Trash** (permanently purges all trashed items from disk).
- `tab`: Toggle selection mark for batch untrash (`u`) or batch purge (`d`).
- `1`-`9`, `0`: Instant restore numbered row directly into prompt bar.

#### Sub-Tab 3: History (`history`)
- `Type text`: Live filter search query.
- `/`: Focus filter input box.
- `ctrl+j` / `ctrl+k`: Load next page / Unload previous page.
- `ctrl+x`: Toggle display of cancelled prompts.
- `ctrl+g`: Edit prompt in external `$EDITOR`.
- `ctrl+y`: Copy prompt text to clipboard.
- `enter`: Submit prompt or load into prompt bar.

---

## 4. Technical Architecture & Storage Design

### 4.1 Storage & Rust Core (`sase-core`)
- Storage file: `~/.sase/prompt_stash_trash.jsonl` (and `~/.sase/prompt_stash_trash.lock`).
- Path helper: `prompt_stash_trash_path()` in [`src/sase/core/paths.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/core/paths.py#L137-L141).
- Rust primitives in `crates/sase_core/src/prompt_stash/trash.rs`:
  - `move_to_prompt_stash_trash`: Atomically pops IDs from `prompt_stash.jsonl`, prepends to `prompt_stash_trash.jsonl`, and enforces `<N>` FIFO pruning.
  - `restore_from_prompt_stash_trash`: Pops IDs from trash and re-appends to active stash.
  - `purge_prompt_stash_trash`: Permanently deletes specific IDs.
  - `clear_prompt_stash_trash`: Truncates trash file.

### 4.2 Configuration Field
In [`src/sase/default_config.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/default_config.yml#L293-L305):
```yaml
ace:
  prompt_stash:
    # Maximum number of deleted prompt drafts to retain in the Stash Trash tab.
    # Older drafts are auto-purged via FIFO eviction. Set to 0 to disable trash.
    trash_limit: 20
```

Accessor in [`src/sase/ace/config.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/config.py): `get_stash_trash_limit() -> int`.

---

## 5. Memory & Glossary Additions

The research report defines the required glossary terms for `sase/memory/glossary/`:

### `Prompt Stash` (alias: `stash`)
> A user-scoped, persistent scratchpad of prompt drafts and templates stored outside prompt history in `~/.sase/prompt_stash.jsonl`. Unlike the immutable, append-only execution log of prompt history, prompt stashes are mutable: drafts can be pinned (`space`) to serve as permanent, reusable templates or left unpinned to pop upon restoration. Managed interactively in the TUI through the Prompts Hub (`@`, `,@`, `Ctrl+G p`, or the top-bar `stash: ≡ N` indicator), where drafts can be restored into the prompt bar, pinned, or moved to stash trash with `d`.

### `Stash Trash` (alias: `trash`)
> Stash trash is the bounded recycling bin for discarded prompt drafts deleted with the `d` keymap from the prompt stash. Stored outside the active stash in `~/.sase/prompt_stash_trash.jsonl`, it serves as an undo and recovery buffer, retaining up to a configurable maximum of `<N>` deleted drafts (default 20, configured via `ace.prompt_stash.trash_limit`). When new entries exceed the limit, older entries are permanently evicted using FIFO pruning. Trashed drafts can be restored directly into the active prompt bar (`enter`), put back into the active prompt stash (`u`), or permanently purged (`d`, `D`).

---

## 6. Artifact & Repository Verification

1. **Research Report Written**:
   - Location: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/unified_prompt_hub_and_stash_trash_design__gem.md`
2. **Durable Snapshot Registered**:
   - Command: `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/unified_prompt_hub_and_stash_trash_design__gem.md" -l "research:202609/unified_prompt_hub_and_stash_trash_design__gem.md"`
   - Output: `ref: file:explicit:1909487c1cd6e200b5b69a24`
3. **Turn Final Declaration**:
   - Submitted and accepted via `sase final submit` for repository obligation `repo-377156487dff` (`sdd:research`).
