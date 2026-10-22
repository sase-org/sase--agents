# Chat History - ace-run (research.3c.gem)

- **TIMESTAMP:** 2026-10-02 12:54:52 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3c.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124120.md`

## Prompt

%id(gem, clan=research.3c)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3c.cdx`, `research.3c.cld`, `research.3c.grk`, `research.3c.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add
excellent support for the recently added memory file history functionality to the TUI
(see the sase-1dr epic bead for context). I'm pretty sure sase's pager is the only thing
that supports memory history at the moment. Can you do some research with the goal of
helping me decide the best way to implement this? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! End your analysis with a
recommended solution. 
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

# Research Report: Architectural Design for Memory History Support in the SASE TUI

**Researcher:** `research.3c.gem`  
**Report Artifact:** `research:202610/memory_history_tui_design__gem.md`  
**Absolute File Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/memory_history_tui_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/memory_history_tui_design__gem.md)  
**Registered Artifact Ref:** `file:explicit:546f1f29da7fdd4f891ef3a4`  

---

### Executive Overview & Findings

Epic `sase-1dr` delivered a foundational, high-performance memory history backend:
- An incremental metadata index in `sase-core` backed by Git as the single store (D1),
- A thread-safe, memoized Python `HistoryService` (`sase.memory.history.service`),
- An expressive CLI (`sase memory history`), and
- A modeless, punctuation-driven time axis in `sase`'s standalone pager (`PagerScreen` / `PagerView`).

However, within the terminal user interface (ACE TUI), memory history currently remains **sequestered inside the pager modal**. Within `MemoryPane` (reached via `g m` or Config Hub `memory`), history is represented only by a static, passive sparkline in the card metadata grid. Exploring history requires pressing `H` (for a single file) or `C` (for the feed), which abruptly launches a full-screen `PagerScreen` modal over the interface.

This creates significant workflow friction:
1. **Context Loss:** Pushing the pager modal obscures the catalog hierarchy. Users cannot easily switch between notes or compare different policy files across time without repeatedly entering and exiting modals.
2. **Catalog Blindness:** The note rail provides zero indication of recency, activity, or churn; active, high-churn files look identical to stable, untouched files.
3. **Tombstone Invisibility:** Deleted memory notes and strands are omitted from the catalog snapshot and cannot be discovered or inspected from the TUI.
4. **Disconnected Agent Context:** Follow-up `sase-1e5` ("Memory as seen by agent") remains unaddressed in the TUI; developers debugging agent behavior cannot see what memory looked like at agent launch.

---

### The Recommended Solution: The "Living Memory" Architecture

Rather than treating history as an external modal destination, `MemoryPane` should become **natively time-aware**. Time should be a fluid, in-place axis across the entire catalog.

The recommended architecture establishes five integrated pillars:

```text
╭─ MEMORY · sase (project) · 14 notes · scope 1/2 ──────────────────────────────────────────────────────────╮
│ NOTES                           │ M MEMORY  gotchas.md  [⟲ PAST · v24 of 25]  1mo ago    sase (project)   │
│ ─────────────────────────────── │ sase/memory/gotchas.md                                                  │
│   ● gotchas.md          ▅  2d   │ ─────────────────────────────────────────────────────────────────────── │
│   ○ cli_rules.md        ▂  1mo  │ ⇧ promoted reference → core · § Keymaps · +31w −4w    sase-1au.5 · 1a2b │
│   ○ dispatch.md         ·  3mo  │ ▁▁▃▁▂▁▇▁▁▂▅▁▁▃▁▂▁▁▅▁▂▁▃▁▆▂▁▃▁▂▁▅▁█▁▂▏ → now   Sep 22 2026 14:03 · v24   │
│   ○ lint_and_test.md    ▃  1w   │ ─────────────────────────────────────────────────────────────────────── │
│   ◆ glossary            █  3h   │   1│ ---                                                                │
│   └ • stitch            ▃  3h   │   2▌ type: core                                                         │
│     • goal              ·  2w   │   3│ ---                                                                │
│   ✖ build_rules.md      ·  del  │   4│                                                                    │
│                                 │   5│ **Default Keymap Config**                                          │
│                                 │   6▌ When changing keymaps, leader mode keys, or any config             │
│                                 │   7▌ values, update `src/sase/default_config.yml` if necessary.         │
│                                 │    ╴                                                                    │
│                                 │ ─────────────────────────────────────────────────────────────────────── │
│                                 │ Type: core (was reference) · Parent: sase · Size: 8 lines · 1a2b3c4     │
├─────────────────────────────────┴─────────────────────────────────────────────────────────────────────────┤
│ Filter notes… (/ to focus, . toggle deleted)                                                              │
├───────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ ( ) step · { } now · = word diff · @ timeline · C feed · \ split · E edit now · q close                   │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```

#### 1. In-Place Time Axis in `MemoryPane`
- **Embedded Time Band:** Mount the `#pager-time` Time Band (meaning row + timeline sparkline scrubber) directly inside `#memory-panel-detail`.
- **In-Place Stepping:** Tapping `(` and `)` steps backward and forward through history directly in the detail pane with sub-6ms cached responsiveness without modal takeover.
- **State Pill & Past Rail:** Renders the violet past accent (`⟲ PAST · v24 of 25`) and vertical gutter line marks (`▌` for added/modified lines, `╴` for deletions).

#### 2. In-Place Reflow-Insensitive Word Diff (`=`)
- Tapping `=` toggles the detail view into the inline word diff view vs. parent (or arbitrary base).
- Struck-through deleted words and highlighted additions flow naturally within sentences without wrapping noise.
- Unchanged lines fold cleanly into expandable `┄ N unchanged lines ┄` blocks.
- Frontmatter mutations display as structured semantic badges (`⇧ type: reference → core`).

#### 3. Temporal Rail & Tombstones (`.`)
- **Activity & Churn Sparklines:** Each note in the left rail gains a 1-cell Unicode sparkline (`·`, `▂`, `▃`, `▅`, `█`) and relative age (`2d`, `1mo`).
- **Tombstone Discovery:** Pressing `.` toggles deleted notes and strands (`✖`). Selecting a tombstone displays its last committed content under a tombstone banner (`✖ DELETED Jul 13 2026 by athena · last content shown`), bringing full auditability to retired policies.

#### 4. Dual-Mode Rail: Integrated Changes Feed (`C`)
- Pressing `C` in `MemoryPane` toggles the left rail into the **Cross-File Changes Feed**, grouped chronologically by day and commit.
- Selecting a commit displays the multi-file impact summary in the detail pane, linking authored causes to rendered consequences (`AGENTS.md` and provider shims).

#### 5. Cross-TUI Bridges ("Memory as Seen by Agent")
- **Agent Data Card Integration (sase-1e5):** The Agents tab gains an explicit `[M View Memory as Seen by Agent]` action that opens `MemoryPane` pinned to the launch commit recorded in the agent's metadata.
- **Clickable Audit Logs:** Pressing `Enter` on an audited read in an agent's log opens that exact historical version.

---

### Implementation Phasing Plan

| Phase | Slug | Core Deliverables |
| :--- | :--- | :--- |
| **Phase 1** | `memory-tui-axis` | Mount Time Band in `MemoryPane`; wire `(`, `)`, `{`, `}`; off-thread hydration in `MemoryPaneHistoryMixin`; past state pills and line marks. |
| **Phase 2** | `memory-tui-diff` | Wire `=` toggle; inline reflow-insensitive word diffs via `word_ops`; unchanged folds; frontmatter semantic blocks; `[`/`]` hunk navigation. |
| **Phase 3** | `memory-tui-rail` | Rail activity sparklines and age badges; deleted subject querying via `HistoryService.subjects()`; `.` tombstone toggle. |
| **Phase 4** | `memory-tui-feed` | `_rail_mode` toggle (`C`); chronological changeset navigation in the left rail with multi-file diff previews. |
| **Phase 5** | `memory-tui-bridges` | `[M View Memory as Seen by Agent]` bridge on Agent Data Cards; `\|` split comparison; audit read link resolution; documentation updates. |

---

### Verification and Artifact Status

1. **Research Report Written:** Saved to [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/memory_history_tui_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/memory_history_tui_design__gem.md).
2. **Artifact Created:** Snapshot created via `sase artifact create` with reference `file:explicit:546f1f29da7fdd4f891ef3a4` and label `research:202610/memory_history_tui_design__gem.md`.
3. **Turn Finalized:** SASE final declaration submitted successfully (`Accepted final declaration for: commit`).
