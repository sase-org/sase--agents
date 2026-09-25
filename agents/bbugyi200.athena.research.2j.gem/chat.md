# Chat History - ace-run (research.2j.gem)

- **TIMESTAMP:** 2026-09-25 07:56:54 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2j.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_074644.md`

## Prompt

%id(gem, clan=research.2j)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2j.cdx`, `research.2j.cld`, `research.2j.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about adding
support to agent data cards (see the sase-17d epic bead for context) for sub-cards,
which I will term "agent data card blocks" (aka "card blocks").

- These should work like decks in that they use a spread view by default and a paged
  view when the merged contents are past a configurable threshold.
- The user should be able to use new `<ctrl+shift+j/k>` keymaps to cycle through the
  currently selected card's blocks.
- Our first use-case for this functionality should be to split the "Main" deck's "Reply"
  card into several blocks (one per sase shell `AGENT CHAT` sub-section). The final card
  (i.e. the last agent's/monitor's/gate's output) should be shown first when this card
  is paged (i.e. viewed as a sequence of blocks). In other words, we should reverse the
  order of the card blocks for the "Reply" card (e.g. `<ctrl+shift+j>` should cycle to
  the 2nd to last sase shell's output block).
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

# Research & Architectural Specification: Sub-Card Partitioning via Agent Data Card Blocks

- **Researcher:** `gem` (swarm member `research.2j.gem`)
- **Report Location:** [`sase/repos/research/202609/agent_data_card_blocks__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/agent_data_card_blocks__gem.md)
- **Snapshot Artifact:** `research:202609/agent_data_card_blocks__gem.md` (`file:explicit:aab3dba1efa80a29463be88d`)

---

## Executive Summary & Core Verdict

The proposal to extend the post-`sase-17d` Agent Data Decks & Cards system with **Agent Data Card Blocks** (sub-cards) is a **high-value, necessary evolutionary step**. 

In modern SASE, an agent run is rarely a single prompt/response interaction; it is a pipeline of **sase shells** (initial execution shell, supervised monitor procs, human/automated review gates, followed by continuation or repair agent shells). Today, all output from these sequential phases is concatenated into a single monolithic `Reply` card (`reply_parts`). This creates severe operational friction: a user inspecting a multi-phase run must scroll past hundreds of lines of historical agent output just to check whether a final gate passed or why a monitor tripped.

Introducing **Card Blocks** establishes a clean, 3-tier navigation hierarchy:
$$\text{Deck (Level 1)} \longrightarrow \text{Card (Level 2)} \longrightarrow \text{Card Block (Level 3)}$$

### Synthesis of Core Questions

1. **Is this a good idea?**
   **Yes.** It directly solves the "heterogeneous scroll deluge" problem in multi-turn/multi-shell sessions and brings the same structural density controls to cards that already exist for decks.
2. **Would we take a different approach?**
   **Yes, specifically regarding nested rendering semantics.** A naive implementation of "spread by default, paged after threshold" at both Deck and Card levels produces a **Two-Level Nesting Paradox**: having an inner card page its blocks while its parent deck is spread. We mandate the **"Spread Deck = Spread Blocks" invariant**: when a deck is rendered in spread mode, all cards and all their blocks are spread on the continuous scroll canvas. Card block paging is strictly active only when a card is inspected in isolation (i.e. when the parent deck is paged).
3. **What adjustments to requirements are justified?**
   - **Terminal Protocol Keymap Fallbacks:** Traditional terminal emulators without Kitty keyboard protocol or XTerm CSI-u cannot distinguish `Ctrl+Shift+J` from `Ctrl+J` (both emit ASCII `0x0A` / LineFeed). Pressing `Ctrl+Shift+J` on standard macOS Terminal.app or legacy tmux will inadvertently trigger `next_deck_card`. We must provide first-class fallback bindings (`[` and `]` on the Agents tab, plus leader shortcuts `, b j` and `, b k`).
   - **Reverse Stack Model for the Reply Card:** We uphold the user's requirement to show the latest shell first in paged mode. In paged mode, blocks are indexed in reverse-chronological order (Block 0 = Latest Shell), with `<ctrl+shift+j>` stepping to the older preceding shell. In spread mode, however, we retain top-to-bottom chronological narrative order, but specify an initial scroll anchor to the latest block's separator.
   - **Visual Beauty via In-Card Phase Navigator Pills:** Rather than overloading the deck panel border title with deep block indices, we specify an **In-Card Phase Navigator Pill** in paged mode and **Titled Block Separators** (`── ⬡ Shell 3: Gate Phase ──`) in spread mode.

---

## Detailed Critique & Architectural Trade-offs

### 1. The Two-Level Spread/Paged Nesting Paradox
If both Decks and Cards independently decide spread vs. paged modes, the matrix produces an invalid state: **Spread Deck + Paged Blocks**.
- If a deck is in spread mode, the user expects to scroll continuously through all cards. If `Reply` internally pages its blocks, blocks 2 and 3 remain invisible while `Context` is visible above it.
- Furthermore, switching blocks via `<ctrl+shift+j>` causes sudden content height reflows in the middle of a scrolling deck, jarring the scroll position.
- **Rule:** When `DeckPanel.is_spread(deck)` is True, all cards render all constituent blocks spread. Block paging is evaluated and activated **only when the deck is in paged mode** (or when a card is solitary). In spread mode, `<ctrl+shift+j/k>` acts as an anchor jump, smoothly scrolling the viewport to the block's titled separator.

### 2. Block Ordering & Directional Semantics
- **Paged Mode:** Blocks are exposed via `card.paged_blocks()`. For cards marked `reverse_paged_order=True` (like `Reply`), the newest shell is at Index 0 (`1 of N: Gate`). `<ctrl+shift+j>` (direction +1) advances from Index 0 (latest) to Index 1 (2nd to last shell), satisfying the user's exact specification.
- **Spread Mode:** Blocks are rendered in execution sequence ($1 \to 2 \to 3$) so the narrative remains coherent, but switching to the card anchors the scroll region directly to the latest block header.

### 3. Keymap Safety across Terminal Emulators
- Modern terminals support `ctrl+shift+j` and `ctrl+shift+k` via CSI-u/Kitty protocol.
- On legacy terminals, `Ctrl+Shift+J` emits ASCII `10` (`\n`), which Textual interprets as `ctrl+j`, cycling the deck card instead.
- We add `next_card_block` / `prev_card_block` to `bindings.py` and `default_config.yml` with primary keys `ctrl+shift+j/k`, and bind `[` and `]` on the Agents tab as dedicated single-key fallbacks (which are currently unused on that tab).

---

## Visual Design Specification

```text
Paged Block Mode: In-Card Phase Navigator Pill
╭─ Shells (3) ─────────────────────────────────────────────────────────────────────────────╮
│  [● 3: Gate Shell (READY)]    [2: CI Watcher (DONE)]    [1: Agent Init (DONE)]          │
│  <ctrl+shift+j/k> or [ / ] to switch shells · 1 of 3 (newest first)                      │
╰──────────────────────────────────────────────────────────────────────────────────────────╯

Spread Block Mode: Visual Rule Hierarchy
━━ ◆ Reply ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ (Card Separator, thick)
                                                                       
── ⬡ Shell 1: Agent Turn ── 10:14:02 ── Done ───────────────────────── (Block Separator, thin)
I have analyzed the repository structure...

── ⬡ Shell 2: CI Watcher ── 10:15:30 ── Done (0) ───────────────────── (Block Separator, thin)
Running `just check`... PASS (42 tests)

── ⬡ Shell 3: Review Gate ── 10:18:45 ── Ready ──────────────────────── (Block Separator, thin)
Host completion prepared. Approval required.
```

- **Border Title Integration:** 
  - Full: `◆ MAIN ┃ Context │ Reply [3/3 · Gate]  2/2`
  - Compact: `◆ MAIN ┃ ‹ 2/2 › Reply [3/3: Gate]`

---

## Technical Architecture & Implementation Blueprint

### 1. Data Model (`src/sase/ace/tui/widgets/decks/card_part.py`)
- Introduce `CardBlock`:
  ```python
  @dataclass(frozen=True, slots=True)
  class CardBlock:
      block_id: str
      title: str
      renderables: tuple[RenderableType, ...]
      subtitle: str | None = None
      glyph: str | None = None
      status: str | None = None
      timestamp: str | None = None
  ```
- Enhance `CardPart`:
  ```python
  class CardPart:
      __slots__ = ("card_id", "title", "renderables", "blocks", "reverse_paged_order")
      def __init__(self, card_id: str, title: str, *renderables: RenderableType,
                   blocks: Sequence[CardBlock] = (), reverse_paged_order: bool = False):
          ...
  ```

### 2. State & Mode Decisions (`model.py` and `render_mode.py`)
- Add `cycle_block_id(block_ids, active, direction)`.
- Add `preferred_blocks: Mapping[str, str]` to `DeckPanelState`.
- Implement `decide_block_render_mode()` with `BLOCK_SPREAD_HYSTERESIS = 0.10` governed by config `ace.agent_decks.card_block_spread_max_screens: 1.5`.

### 3. Prompt Panel Refactoring (`_agent_display_render.py`)
- Implement `build_reply_card_blocks(agent, render_markdown)`:
  - Block 1: Initial agent shell.
  - Blocks 2..N: Follow-up monitors (`shell-mon-*`), gates (`shell-gate-*`), and successor agent runs.
- Construct `CardPart(REPLY_CARD_ID, REPLY_CARD_TITLE, blocks=blocks, reverse_paged_order=True)`.

### 4. Implementation Phasing
1. **Phase 1: Pure Data Model:** `card_block.py`, `CardPart` updates, unit tests.
2. **Phase 2: Render Engine & Separators:** `_BlockSeparator`, `DECK_BLOCK_META_KEY`, anchor indexing.
3. **Phase 3: View & Panel Integration:** `MainDeckView` block spread/paged rendering, `scroll_to_block`.
4. **Phase 4: Actions & Keymaps:** `action_next_card_block` / `prev_card_block`, `ctrl+shift+j/k` + `[` / `]` fallbacks.
5. **Phase 5: Reply Card Wiring & Verification:** Partition agent sessions into blocks, generate targeted PNG goldens, verify p95 perf stays $<16\text{ ms}$.

The complete, unabridged research document has been written to [`sase/repos/research/202609/agent_data_card_blocks__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/agent_data_card_blocks__gem.md) and registered as snapshot `research:202609/agent_data_card_blocks__gem.md`.
