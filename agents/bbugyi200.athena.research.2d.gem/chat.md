# Chat History - ace-run (research.2d.gem)

- **TIMESTAMP:** 2026-09-23 17:46:25 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2d.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260923_173402.md`

## Prompt

%id(gem, clan=research.2d)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2d.cld`, `research.2d.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think I want to redesign the agent
metadata panel and files/LLM calls panels on the "Agents" tab.

- Namely, I want to unify these using a new concept that I will name "agent data
  decks/cards" (aka "decks/cards"). Appropriate glossary memory web strands should be
  added.
- Instead of supportig two different types of panels (the agent metadata panel and the
  files/LLM calls panel), we will support just one panel type (a "deck panel") that
  hosts one or more agent data cards.
- Deck panels will render their cards dynamically based on the size of their contents.
  - We will prefer to render all cards on the same page (with clear, visually appealing
    separation of cards) if the size of the panel would not be forced to go over some
    configurable (via a new sase config field) threshold.
  - If that threshold is crossed, then we should render each card on its own page which
    the user can cycle through using the `<ctrl+shift+n/p>` keymaps, which you will need
    to add. This is inspired by how the files panel currently works. In fact, when the
    combined size of the files crosses our configured threshold, we should be able to
    cycle through the different files that used to be shown in the files panel in the
    "Files" deck (one card per file).
- How should the current contents of the agent metadata panel and files/LLM calls panels
  be migrated to decks/cards?
  - The agent metadata panel should be migrated to a "Main" deck that contains two
    cards:
    - One named "Context" that contains the `SASE CONTEXT`, `SLOW TOOLS`,
      `AGENT XPROMPT`, and `AGENT PROMPT` sections (this card should also contain any
      sections / content that I am forgetting about). This should be the default card
      shown (though the entire "Main" deck should be shown if it doesn't cross the
      threshold).
    - One named "Reply" that contains the `AGENT REPLY` section.
  - The migration for the files panel is described above.
  - The LLM calls panel should be migrated to a "Tools" deck with a single card for now
    (I plan on adding another card that works with the `sase tool` command at some point
    later).
- We should support two different "deck layouts" to start (controlled by the `\` / `|`
  keymaps described below):
  - A vertical layout with one deck on the left and one on the right.
  - A horizontal layout with one deck on the top and one on the bottom.
- We will need to add the following keymaps to the "Agents" tab:
  - `<ctrl+shift+n/p>`: Described above.
  - `<ctrl+n/p>`: Used to cycle the currently focused deck panel to the next/previous
    deck.
  - `\`: Used to create a new horizontal split (i.e. add a new deck panel below the
    current deck).
  - `|`: Create a new horizontal split (i.e. add a new deck to the right of the current
    deck panel).
  - `<ctrl+s>`: Used to collapse/expand the panel of nodes shown on the left of the
    "Agents" tab. Support for collapsing the node panel will be useful/necessary for
    vertical deck splits (and obsoleting the zoom panel, which should probably be done
    as a part of this work). Think hard about the best way to represent a collapsed node
    panel.
  - `<ctrl+f>`: Used to toggle which deck panel is currently focused. This should be
    used to control which panel we are acting on.
- More on the `\` and `|` keymaps:
  - We should automatically open the next, not currently shown, deck (if any--otherwise,
    show the current deck) when these keymaps are used and there is only one deck shown
    at the moment.
  - If a vertical split already exists and the `|` keymap is used, we should go back to
    showing a single deck (we should do the same thing for the `\` keymap when a
    horizontal split is already shown).
  - If the opposite type of split is currently shown when these keymaps are used, then
    we should keep the current decks visible but switch the layout accordingly.
- The panel that is triggered by the `p` keymap on the "Agents" tab currently can
  probably just be removed.

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

# Research & Architectural Critique: Unifying Agent Metadata, Files, and Tools via Agent Data Decks and Cards

- **Researcher:** `research.2d.gem`
- **Report Location:** [`sase/repos/research/202609/agent_data_decks_and_cards__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/agent_data_decks_and_cards__gem.md)
- **Snapshot Artifact:** `file:explicit:e784e9e53894af7f1bea46fb` (`research:202609/agent_data_decks_and_cards__gem.md`)

---

## 1. Executive Summary & Assessment

The proposal to unify the **agent metadata panel** and the **files / LLM calls panels** into a single generic **Deck Panel** hosting **Agent Data Cards** is an **exceptional architectural leap forward**. 

The current Agents tab detail implementation is heavily fragmented:
1. `AgentPromptPanel` is a monolithic vertical scroll widget concatenating disparate concerns (identity headers, rosters, output variables, SASE context, slow tools, xprompts, prompts, and streaming reply tokens).
2. The secondary panel alternates awkwardly between two entirely distinct widgets (`AgentFilePanel` and `AgentLLMCallsPanel`).
3. Layout sizing is driven by a modal dialog (`AgentViewModal`, triggered by `p`) that toggles rigid vertical percentages (70/30, 50/50, 30/70) rather than direct keyboard splits.
4. The files panel enforces a strict 1-file-per-page model even when an agent changed three tiny 4-line files, forcing constant `<ctrl+n/p>` flipping.
5. Detail zooming requires an isolated modal screen (`ZoomPanelModal`, `Z`), duplicating roughly 2,500 lines of widget code and severing normal live interaction.

The **Decks and Cards** mental model solves each of these issues cleanly:
- **Uniformity:** Replaces three ad-hoc panel types with one reusable `DeckPanel` widget.
- **Composability:** Encapsulates cohesive inspection surfaces into named decks (`Main`, `Files`, `Tools`).
- **Adaptive Density:** Automatically renders all cards on one scrollable page when total size falls within a configurable threshold, paginating only when content is large.
- **Tactile Splits:** Introduces direct vim/tmux-style split controls (`\` for horizontal, `|` for vertical) with single-key toggles and orientation flipping.
- **Code Pruning:** Retires both the modal picker (`p`) and the zoom modal (`Z`) by pairing deck splits with a collapsible node panel (`<ctrl+s>`), removing ~2,500 lines of redundant code.

---

## 2. Critique of the Requirements & Necessary Adjustments

Our independent analysis identified **four critical friction points** in the proposed plan that require specific adjustments:

### 1. Conflict with `<ctrl+f>` Focus Toggling
- **The Issue:** In SASE's default keymap configuration (`src/sase/default_config.yml:587` and `src/sase/ace/tui/bindings.py:71`), `<ctrl+f>` is bound to `scroll_prompt_down` (the standard Vim full-page down motion). Reassigning `<ctrl+f>` unconditionally breaks page-down navigation for Vim users.
- **Adjustment:** Support `<ctrl+f>` for deck focus toggling as requested, but also register **`<Tab>`** and **`<ctrl+w><ctrl+w>`** as alternate bindings. Document the scrolling migration to rely on `<ctrl+d>` (half-page down) and `<PageDown>`.

### 2. Terminal Transport Vulnerability for `<ctrl+shift+n/p>`
- **The Issue:** Many standard terminal emulators (e.g. GNOME Terminal, Windows Terminal, browser terminals) do not pass modified control combinations. Under legacy terminal protocols, `Ctrl+Shift+N` emits byte `0x0E`—the exact same byte as `Ctrl+N`. In GNOME Terminal, `Ctrl+Shift+N` spawns a new OS terminal window. Without fallbacks, users pressing `<ctrl+shift+n>` will cycle *decks* instead of *cards*.
- **Adjustment:** Provide conflict-free primary/secondary keybindings:
  - **`]` / `[`** (Next Card / Prev Card): Matches Vim tag/bracket navigation and directly mirrors the existing `next_panel`/`prev_panel` bindings from `ZoomPanelModal`.
  - Configured keymap: `cycle_card_forward: "ctrl+shift+n,right_square_bracket"`.

### 3. Threshold Metric & Streaming Hysteresis
- **The Issue:**
  - Measuring rendered screen height in cells causes layout thrashing and depends on window resize reflows.
  - If threshold is small, prompts will almost always force pagination, preventing continuous mode.
  - While an agent is streaming live output, the cumulative size will grow past the threshold. If pagination triggers abruptly mid-stream, the viewport will jump jarringly.
- **Adjustment:**
  - Define the threshold strictly as **logical line count**: `ace.deck_cards_threshold: 80` (lines).
  - Implement **streaming hysteresis**: When the threshold is crossed during active agent execution, preserve view focus on the actively updating card (Reply) and smoothly transition the header status to `[Card 2/2: Reply (paged)]` without bouncing the scroll view.

### 4. Collapsed Node Panel Representation (`<ctrl+s>`)
- **The Issue:** The prompt asked to *"think hard about the best way to represent a collapsed node panel."* Completely hiding the panel (`width: 0`) creates total context loss: the user cannot tell which agent is active, cannot monitor running background agents, and loses `j/k` navigation across agents.
- **Recommended Representation: The Micro-Rail (Width 4 Cells)**
  - When collapsed via `<ctrl+s>`, `#agent-list-container` shrinks from `width: 60` to `width: 4`.
  - Displays a compact 2-to-3 character glyph cluster per row:
    - Col 1: Selection marker (`▎` for active row).
    - Col 2: Status indicator (`✓` green done, `✗` red failed, `⟳` cyan running, `⏸` yellow gate).
    - Col 3: Role tag (`p` plan, `c` code, `e` epic, `m` monitor, `g` gate, `j` job).
  - Reclaims 56 horizontal columns for deck panels while allowing the user to keep the list collapsed and continue pressing `j`/`k` to navigate agents.

---

## 3. Deck & Card Architecture

```text
┌────────────────────────────────────────────────────────────────────────┐
│ TopBar / TabBar / Indicators                                          │
├──────┬─────────────────────────────────────────────────────────────────┤
│ Rail │ Deck Panel 0 (Primary - Focused)   │ Deck Panel 1 (Secondary)   │
│ (W:4)│ ┌────────────────────────────────┐ │ ┌────────────────────────┐ │
│ ▎✓c  │ │ Deck: Main [Card 1/2: Context] │ │ │ Deck: Files [3 Cards]  │ │
│  ⟳p  │ ├────────────────────────────────┤ │ ├────────────────────────┤ │
│  ·e  │ │ SASE CONTEXT                   │ │ │ ─── src/sase/foo.py ── │ │
│      │ │ SLOW TOOLS                     │ │ │ +12, -4 diff           │ │
│      │ │ AGENT XPROMPT                  │ │ │ ─── tests/test_foo.py─ │ │
│      │ │ AGENT PROMPT                   │ │ │ +30, -0 diff           │ │
│      │ └────────────────────────────────┘ │ └────────────────────────┘ │
└──────┴────────────────────────────────────┴────────────────────────────┘
```

### 1. "Main" Deck
- **Card 1: "Context" (Default Card)**
  - Header identity metadata, runner queue position, family/clan roster, output & workflow variables.
  - `SASE CONTEXT` section: beads, plans, memory reads, glossary reads, skill uses, touches, deltas, opened workspaces, artifact reads.
  - `SLOW TOOLS` section: slow tool call summaries.
  - `AGENT XPROMPT`: humanized and raw xprompts.
  - `AGENT PROMPT`: initial system instructions.
  - Error banner and stack trace (if failed).
- **Card 2: "Reply"**
  - `AGENT REPLY` / `AGENT CHAT` heading.
  - Streaming live reply tokens & timestamped chunks.
  - Multi-attempt history (`attempt_view_mode == "merged"` or pinned attempt).
  - Follow-up agent execution phases (monitors, gates).
  - Final response text or structured step output.

### 2. "Files" Deck
- **Cards:** Dynamic, 1 card per modified file or diff slot (live diff, workspace diff, static read, linked delta, commit diff).
- **Adaptive Paging:**
  - Cumulative diff $\le 80$ lines: All files render in one continuous scroll view with distinct card divider banners.
  - Cumulative diff $> 80$ lines: Files paginate into individual cards, cycled via `<ctrl+shift+n/p>` or `[` / `]`.

### 3. "Tools" Deck
- **Card 1: "LLM Calls"**: Normalized tool-call artifact timeline (`tool_calls.jsonl`) with `h`/`l`/`H`/`L` detail toggling.
- **Card 2: "Named Tools"**: Future integration for `sase tool` command runner records.

---

## 4. Keymap Design & Split State Machine

### Keymaps
| Key | Action | Function | Notes |
| :--- | :--- | :--- | :--- |
| `<ctrl+n>` | `cycle_deck_forward` | Cycle focused panel to next deck (`Main` $\to$ `Files` $\to$ `Tools`) | Replaces old file cycling. |
| `<ctrl+p>` | `cycle_deck_backward` | Cycle focused panel to previous deck (`Tools` $\to$ `Files` $\to$ `Main`) | Replaces old file cycling. |
| `<ctrl+shift+n>` / `]` | `cycle_card_forward` | Cycle card forward within focused deck (when paged) | `]` provided as universal fallback. |
| `<ctrl+shift+p>` / `[` | `cycle_card_backward` | Cycle card backward within focused deck (when paged) | `[` provided as universal fallback. |
| `\` | `toggle_deck_split_horizontal` | Add/toggle horizontal split (deck panel below) | Toggles single panel $\leftrightarrow$ stacked panels. |
| `\|` | `toggle_deck_split_vertical` | Add/toggle vertical split (deck panel to the right) | Toggles single panel $\leftrightarrow$ side-by-side panels. |
| `<ctrl+s>` | `toggle_node_panel_collapsed` | Collapse / expand left node panel (width: 4 vs 60) | Frees 56 cols; obsoletes `ZoomPanelModal`. |
| `<ctrl+f>` / `<Tab>` | `toggle_deck_focus` | Switch focus between Deck Panel 0 and Deck Panel 1 | `<Tab>` registered as fallback. |
| `p` | *(Removed)* | Deprecates `choose_agent_view` modal picker | Obsoleted by direct split/cycling keys. |
| `Z` | *(Removed)* | Deprecates `zoom_panel` modal screen | Obsoleted by `<ctrl+s>` list collapse. |

### Split State Machine (`\` and `|`)
- **From Single Panel (`NONE`):**
  - Pressing `|` opens the next unshown deck to the right (`VERTICAL` split).
  - Pressing `\` opens the next unshown deck below (`HORIZONTAL` split).
- **From Split (`VERTICAL` or `HORIZONTAL`):**
  - Pressing the **same key** as the active split (`|` in `VERTICAL`, or `\` in `HORIZONTAL`) collapses the view back to a single deck panel, expanding the currently focused deck.
  - Pressing the **opposite key** (`\` in `VERTICAL`, or `|` in `HORIZONTAL`) preserves both currently visible decks and rotates the container orientation (columns $\leftrightarrow$ rows).

---

## 5. Memory Web Glossary Strands

The research report contains the complete authored drafts for the three required glossary strands:
1. **`sase/memory/glossary/agent-data-deck.md`**: Defines an Agent Data Deck as a named, coherent collection of agent data cards presented on the Agents tab.
2. **`sase/memory/glossary/agent-data-card.md`**: Defines an Agent Data Card as an atomic presentation unit within a deck with self-contained rendering and logical line counts.
3. **`sase/memory/glossary/deck-panel.md`**: Defines a Deck Panel as the viewport container widget hosting an active deck with support for horizontal and vertical splits.

---

## 6. Phased Implementation Roadmap

1. **Phase 1: Foundation Models & DeckPanel Widget**
   - Author memory strands in `sase/memory/glossary/`.
   - Implement `AgentCard`, `AgentDeck`, and `DeckPanel` in `src/sase/ace/tui/decks/`.
   - Separate `AgentPromptPanel` into `ContextCard` and `ReplyCard`.
   - Wrap `AgentFilePanel` files into `FileCard` instances and `AgentLLMCallsPanel` into `LLMCallsCard`.
   - Add `ace.deck_cards_threshold: 80` to `default_config.yml` and `sase.schema.json`.
2. **Phase 2: Split Controls & Navigation**
   - Implement deck cycling (`<ctrl+n/p>`) and card cycling (`<ctrl+shift+n/p>`, `[` / `]`).
   - Implement split toggling and rotation (`\`, `|`) in `AgentDetail`.
   - Implement focus switching (`<ctrl+f>`, `<Tab>`).
3. **Phase 3: Node List Collapse (`<ctrl+s>`) & Micro-Rail**
   - Implement `toggle_node_panel_collapsed` action.
   - Style the 4-cell micro-rail in `styles.tcss`.
   - Verify `j/k` row selection updates detail decks seamlessly while collapsed.
4. **Phase 4: Cleanup & Deprecations**
   - Delete `AgentViewModal` (`p`) and `ZoomPanelModal` (`Z`) and their tests.
   - Rebase TUI screenshots and verify visual golden fixtures.

---

### Registered Deliverables
- **Research Document:** [`sase/repos/research/202609/agent_data_decks_and_cards__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/agent_data_decks_and_cards__gem.md)
- **Durable Snapshot:** `file:explicit:e784e9e53894af7f1bea46fb` (`research:202609/agent_data_decks_and_cards__gem.md`)
- **Finalizer Declaration:** Submitted and accepted (`commit` for `sdd:research`).
