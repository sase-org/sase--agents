# Chat History - ace-run (research.h.gem)

- **TIMESTAMP:** 2026-09-27 16:20:03 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.h.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_161058.md`

## Prompt

%id(gem, clan=research.h)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.h.cdx`, `research.h.cld`, `research.h.grk`, `research.h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently support
collapsing the nav sidebar on the "Agents" tab via the `<ctrl+s>` keymap.

- We also support zooming in on a single deck using the `Z` keymap, in which case the
  sidebar is also collapsed.
- When the sidebar is collapsed, it is completely invisible currently.
- This is the correct behavior when zoomed, but should not be the default format used
  when collapsing the sidebar using the `<ctrl+s>` keymap.
- Instead, every tribe, agent group (e.g. "Running"), and node should be represented
  still, just in a collapsed, fixed width state.
- I'm thinking we can use some of the icons we already support (and maybe add a few more
  if needed--for example, I'm not sure if every type of agent group has a corresponding
  icon) to accomplish this, but you should decide. Think hard about what the best UX for
  this is.
- As a part of this change, let's make it clearer (in a visually appealing way) when a
  deck is zoomed (so the user can't mistakenly think the sidebar is just collapsed).
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

# Research Report: Agents Tab Collapsed Nav Sidebar & Deck Zoom UX Design

**Report File**: [`agents_tab_collapsed_nav_and_zoom_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202609/agents_tab_collapsed_nav_and_zoom_ux__gem.md)  
**Registered Artifact**: `research:202609/agents_tab_collapsed_nav_and_zoom_ux__gem.md` (`file:explicit:0c7f58f4ec00edb6c46800a4`)  
**Researcher**: `research.h.gem`

---

## 1. Executive Summary & Core Recommendation

Currently in the SASE Textual TUI (`src/sase/ace/tui/`), collapsing the navigation sidebar via `<ctrl+s>` (`toggle_node_panel`) and zooming into a deck panel via `Z` (`toggle_deck_zoom`) are architecturally coupled behind `DeckAreaState.nodes_collapsed = True`. Both paths invoke `_sync_nodes_collapsed_chrome()`, which attaches the `-nodes-collapsed` CSS class to `#agents-content`, hiding `#agent-list-container` completely (`display: none;`) and showing only a bare 2-cell scrollbar minimap (`#agent-node-spine`).

This leads to:
1. **Total blindness on `<ctrl+s>`**: Collapsing the sidebar hides all tribes, group headers, running agents, and failure indicators.
2. **Ambiguity with Zoom (`Z`)**: In a single-panel layout, pressing `<ctrl+s>` and pressing `Z` look virtually identical. The only distinction in the entire interface is a 4-character dim label (`zoom`) in the top `AgentInfoPanel`.

### The Recommended Solution
We recommend **completely decoupling sidebar collapse from deck zoom**:
1. **Nav Sidebar Collapse (`<ctrl+s>`) -> The Compact Nav Rail (6 columns wide)**:
   - Instead of setting `display: none;`, `<ctrl+s>` transitions `#agent-list-container` into a fixed **6-column Compact Nav Rail**.
   - `AgentList` remains mounted, focused, and navigable via `j`/`k`, rendering a high-density, glanceable icon grammar:
     - **Tribes** render as section dividers featuring configured tribe icons (`⌂`, `▲`, `†`, `◆`, `◉`).
     - **Agent Groups** across all grouping modes (`BY_STATUS`, `STANDARD`, `BY_DATE`, `BY_MACHINE`) render bracketed category glyphs with agent count chips (e.g., `[▶] 4`, `[⏳] 2`, `[✗] 1`, `[◫] 3`, `[⑂] 2`, `[⏱] 6`).
     - **Agent Nodes** render provider emoji badges (`🟣`, `🟢`, `🔵`), live status glyphs, and turn/attempt micro-disambiguators (`#1`, `#2`, `?`).
   - Recovers **54 terminal columns** for active documents while preserving 100% fleet situational awareness.
2. **Deck Zoom (`Z`) -> Pure Cinematic Full-Bleed Focus (100% width)**:
   - Zoom completely removes all sidebar elements (`display: none;` on both `#agent-list-container` and `#agent-node-spine`).
   - The focused deck panel expands to 100% terminal width and receives Textual's **double border** (`border: double #FFD700;`).
   - The deck header displays an unmistakable elevated badge: `[ ⤢ ZOOMED (1 of 2) ] · Z to restore`.

---

## 2. Critique of the Plan & Justified Adjustments

### Critique 1: The "Split Decks with Hidden Sidebar" Gap
- **Finding**: If `<ctrl+s>` *only* collapses the sidebar to a 6-column rail, and *only* `Z` completely hides the sidebar, users who use split decks (e.g. 50/50 split of Main Document and Files/Diffs) can never view split decks full-screen without a sidebar, because `Z` forces `DeckLayout.SINGLE`.
- **Adjustment**: While `<ctrl+s>` should toggle between `Expanded` and `Compact Rail` by default, provide a secondary keybinding (or an opt-in 3-state toggle cycle `Expanded -> Compact Rail -> Hidden -> Expanded`) so split-deck users can still achieve a 100% borderless view when desired.

### Critique 2: The "Identical Icon / Homogeneity" Problem in Dense Rosters
- **Finding**: If a tribe contains 10 running Claude worker agents, an icon-only representation displays 10 consecutive rows of `🟣 ▶`. Without text, individual agents become indistinguishable.
- **Adjustment**:
  1. **Instant Top-Bar Synchronization**: Moving the cursor (`j`/`k`) over a compact row immediately synchronizes `AgentInfoPanel` and the deck title with the full agent name and prompt summary.
  2. **Micro-Disambiguators**: Dedicate columns 3–4 of the rail to numeric attempt tokens (`#1`, `#2`), unread attention dots (`●`), or input pauses (`▲` / `?`).
  3. **Rich Tooltips**: Tooltips on cursor pause display the full agent identity without expanding the rail.

### Critique 3: Header vs. Node Visual Distinction
- **Finding**: If a group banner for "Running" uses `▶` and a node in that group also uses `▶`, the rail becomes visually chaotic.
- **Adjustment**: Distinct visual grammar:
  - **Tribes**: Full-width solid accent divider with tribe icon (e.g., `[@⌂]──`).
  - **Group Banners**: Bracketed category chips with counts (e.g., `[▶] 4`, `[✗] 1`).
  - **Agent Nodes**: Left-anchored selection border `▌` + provider icon + status glyph.

---

## 3. Visual & UX Specifications

### 3.1 Compact Nav Rail Geometry (Width 6)

```text
 Column:  0   1   2   3   4   5
 Token:  [S] [P] [T] [D] [G] [│]
```
- `[S]` (Col 0): Selection indicator (`▌` in bold gold `#FFD700`), marked check (`✓`), or fold armed marker (`▿`).
- `[P]` (Col 1): Provider badge (`🟣` Claude, `🟢` OpenAI, `🔵` Gemini) or type glyph (`⚙` Monitor, `⧖` Gate, `❯` Step).
- `[T]` (Col 2): Live status glyph (`▶` Running, `⏳` Waiting, `▲`/`?` Asking, `✓` Done, `✗` Failed).
- `[D] [G]` (Cols 3–4): Disambiguation / index (`#1`, `#2`, `!`, `●` unread, `✏️` diff).
- `[│]` (Col 5): Dim vertical border rule separating the rail from the deck panel.

#### ASCII Comparison: Expanded Sidebar vs. Compact Nav Rail

```text
EXPANDED SIDEBAR (60 columns)
┌──────────────────────────────────────────────────────────┐
│ @epic clan:feature-auth                                  │
│ ▌ sase-org/sase ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2 running  │
│   ▎ ⑂ sase-4012 (auth-oauth) ────────────────── 2 agents │
│ [a] ▌ 🟣 review.h.claude (RUNNING 01:24) ─────── %r12    │
│ [b]   🔵 review.h.gemini (WAITING INPUT) ─────── %r13    │
│   ▎ ⑂ sase-4015 (login-fix) ─────────────────── 1 failed │
│ [c]   🟢 auth.coder (FAILED exit:1) ──────────── %r14    │
└──────────────────────────────────────────────────────────┘

COMPACT NAV RAIL (6 columns)
┌────┐
│[@▲]│  <- Tribe: @epic
│[◫]3│  <- Project: sase-org/sase (3 agents)
│[⑂]2│  <- Patch: sase-4012
│▌🟣▶│  <- Row a: Selected (▌), Claude, Running
│ 🔵▲│  <- Row b: Gemini, Needs Input (Gold ▲)
│[⑂]1│  <- Patch: sase-4015
│ 🟢✗│  <- Row c: OpenAI, Failed (Red ✗)
└────┘
```

### 3.2 Icon Catalog Extensions

| Category | Group / Entity | Current Glyph | Proposed Collapsed Token | Color / Style |
|---|---|:---:|:---:|---|
| **BY_STATUS** | `Stopped` (Needs Input) | `▲` | `[▲] N` | Bold Gold (`#FFD700`) |
| | `Starting` | `◐` | `[◐] N` | Dim Cyan (`#5FD7FF`) |
| | `Running` | `▶` | `[▶] N` | Bold Sky Blue (`#87AFFF`) |
| | `Queued` | `…` | `[…] N` | Muted Blue (`#5F87FF`) |
| | `Waiting` | `⏳` | `[⏳] N` | Lavender (`#AF87FF`) |
| | `Failed` | `✗` | `[✗] N` | Bold Red (`#FF5F5F`) |
| | `Done` | `✓` | `[✓] N` | Soft Green (`#87D787`) |
| **STANDARD** | L0: Project | `▌` | `[◫] N` *(New)* | Bold Sky Blue (`#5FAFFF`) |
| | L1: Patch (CL/PR) | `▎` | `[⑂] N` *(New)* | Light Cyan (`#87D7FF`) |
| | L2: Name-Root | `▸` | `[▸] N` | Dim Teal (`#87D7AF`) |
| **BY_DATE** | L0: `Today` | None | `[⏱] N` *(New)* | Bold Sky Blue (`#5FAFFF`) |
| | L0: `Yesterday` | None | `[◷] N` *(New)* | Sky Blue (`#5FAFFF`) |
| | L0: `This Week` | None | `[📅] N` *(New)* | Dim Sky Blue (`#5FAFFF`) |
| | L0: `Earlier` | None | `[🗄] N` *(New)* | Dim Muted (`#888888`) |
| **BY_MACHINE** | L0: Local (`here`) | None | `[⌂] N` | Bold Cyan (`#5FD7FF`) |
| | L0: Remote Machine | `⇄` | `[⇄] N` | Bright Cyan (`#5FD7FF`) |
| **TRIBES** | `@default`, `@epic`, etc. | Text | `[@⌂]`, `[@▲]`, `[@†]` | Defined Tribe Color |

---

## 4. Zoom Mode: Cinematic Visual Focus

```text
┌────────────────────────────────────────────────────────────────────────────────────────────────┐
│ ╔═ [ ⤢ ZOOMED: PANEL 1 OF 2 ] ═ ⬡ MAIN DOCUMENT ═════════════════════════════ Z to restore ═╗ │
│ ║                                                                                            ║ │
│ ║  # Implementation Plan: Authentication Overhaul                                            ║ │
│ ║                                                                                            ║ │
│ ║  This document outlines the multi-provider authentication migration...                    ║ │
│ ║                                                                                            ║ │
│ ╚════════════════════════════════════════════════════════════════════════════════════════════╝ │
└────────────────────────────────────────────────────────────────────────────────────────────────┘
```

1. **Total Sidebar Elimination**: No 6-column rail, no 2-cell spine. Column 0 to terminal edge is 100% dedicated to the deck.
2. **Elevated Double Gold Border**: Uses Textual's `border: double #FFD700;`. An unmistakable visual signal of a maximized modal state.
3. **High-Contrast Header Badge**: In `src/sase/ace/tui/widgets/decks/titles.py`, injects `[ ⤢ ZOOMED ]` in `bold reverse #FFD700` alongside an explicit exit hint (`Z to restore`).
4. **Header Banner Pill**: `AgentInfoPanel` highlights `⤢ ZOOM ACTIVE (Z exits)`.

---

## 5. Implementation Architecture & Performance Safety

In accordance with `sase/memory/tui_perf.md` (Rules 2, 5, 6, 12):
1. **Model Decoupling**: Introduce `NavSidebarMode` (`EXPANDED`, `COMPACT_RAIL`, `HIDDEN`) on `DeckAreaState`. `toggle_nodes_collapsed()` toggles `COMPACT_RAIL`, while `_enter_zoom()` selects `HIDDEN` and sets `-zoomed` on the deck area.
2. **CSS-Driven Layout Transitions**: `#agent-list-container.-compact` handles dimensions (`width: 6; min-width: 6; max-width: 6;`) without unmounting or rebuilding widgets.
3. **Dual-Key Caching**: Update `AgentRenderCache` to include `is_compact: bool` in its render keys (`(identity, status, is_selected, is_compact)`), ensuring toggling `<ctrl+s>` requires zero full agent list allocations and completes well under SASE's 16 ms p95 key-to-paint budget.

---

## 6. Artifact Registration & Hand-off

The complete, unabridged research document has been written and persisted:
- **Workspace Path**: [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202609/agents_tab_collapsed_nav_and_zoom_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202609/agents_tab_collapsed_nav_and_zoom_ux__gem.md)
- **Durable Snapshot**: `sase artifact create` succeeded with ID `explicit:0c7f58f4ec00edb6c46800a4` and label `research:202609/agents_tab_collapsed_nav_and_zoom_ux__gem.md`.
- **Finalizer Declaration**: Turn completed through `sase final submit` with Conventional Commit declaration for `sdd:research`.
