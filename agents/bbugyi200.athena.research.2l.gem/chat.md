# Chat History - ace-run (research.2l.gem)

- **TIMESTAMP:** 2026-09-26 09:43:30 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2l.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_093123.md`

## Prompt

%id(gem, clan=research.2l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2l.cdx`, `research.2l.grk`, `research.2l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Once card blocks are
fully implemented (see the sase-19x epic bead for context), I want to improve the UX to
make it clear whether the spread or paged view is enabled for a deck and/or card. I also
want to add one or more new keymaps that allow the user to toggle through the 3 states
(fully spread, paged deck and spread card, paged deck and paged card).

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about what the best UX for this functionality is. End your analysis
with a recommended solution. 
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

Wait for task-36 to complete.<SYSTEM_MESSAGE>
[Message] timestamp=2026-09-26T13:36:00Z sender=02ddac38-5ae0-4149-b95d-35b0459bcea4/task-36 priority=MESSAGE_PRIORITY_HIGH content=Task id "02ddac38-5ae0-4149-b95d-35b0459bcea4/task-36" finished with result:

The command exited with code 0.
Output:
<truncated 10 lines>
  - In single-panel and horizontal splits, an unpinned scroll stays pinned to the
    bottom when content arrives at the bottom, matching today's behaviour.

### 3.3 Spread versus paged decisions

There are now two spread/paged decisions:

1. **Deck spread vs paged** (existing): does the deck show all cards concatenated or one
   card at a time? Decided by `decide_render_mode` across all cards, with
   `spread_max_screens` (default 2.5). When a deck is spread, every card is spread.
2. **Card block spread vs paged** (new): when a card is **shown alone** (the deck is
   paged), does it show all its blocks concatenated or one block at a time? Decided by
   `decide_block_mode` over the card's blocks, with `block_spread_max_screens` (default
   1.5).

Both decisions:

- share the same hysteresis band (`spread_hysteresis_rows(viewport_rows) = max(2, min(8, viewport_rows // 6))`)
  so borders never oscillate under streaming
- use the exact height measurement with the same cheap line-count lower bound
- can be forced via config: `spread_max_screens: 0` forces deck-paged;
  `block_spread_max_screens: 0` forces block-paged; large values force spread
- re-decide on window resize and split/ratio changes

A card whose blocks are paged is called **block-paged**. A card whose blocks are spread
is called **block-spread**. A deck whose cards are spread is called **deck-spread**.


Log: file:///home/bryan/.gemini/antigravity-cli/brain/02ddac38-5ae0-4149-b95d-35b0459bcea4/.system_generated/tasks/task-36.log
</SYSTEM_MESSAGE>
# Research Report: Deck and Card Spread vs. Paged View UX & Keymap Design

**Researcher**: `gem` (`research.2l.gem`)  
**Report Artifact Reference**: [`research:202609/deck_and_card_spread_paged_toggle_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/deck_and_card_spread_paged_toggle_ux__gem.md)  
**Artifact ID**: `file:explicit:2912e8cf1d5e48e91006fc94`  
**Absolute File Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/deck_and_card_spread_paged_toggle_ux__gem.md`  

---

## 1. Executive Summary & Recommended Solution

With the introduction of shell-level **Card Blocks** (`sase-19x`) in the ACE TUI, the detail pane operates on a three-tier hierarchy: **Deck → Card → Block**. There are two layout presentation axes:
1. **Deck Axis**: All cards concatenated on one scrollable canvas (**Deck Spread**) vs. one card shown alone (**Deck Paged**).
2. **Card Block Axis**: When a card is shown alone, all of its shell blocks concatenated inline (**Block Spread**) vs. partitioned into single-shell pages (**Block Paged**).

Currently, both decisions are automatic based on viewport screen budgets (`spread_max_screens = 1.5`, `block_spread_max_screens = 1.5`), leaving users without clear visual indication of the current mode or direct manual control.

### The Recommended Architecture:

1. **The 3-State Information Density Ladder**:
   - **State 1: Fully Spread** (`DECK_SPREAD`): All cards (`Context`, `Prompt`, `Reply`) concatenated inline; all card blocks inline; block rail hidden.
   - **State 2: Paged Deck, Spread Card** (`CARD_SPREAD`): Active card shown alone; all shell blocks rendered inline; block rail visible as a scroll/anchor timeline.
   - **State 3: Paged Deck, Paged Card** (`CARD_PAGED`): Active card shown alone; single shell block rendered per page; block rail visible as a page-flip timeline.
   *(The 4th permutation—Deck Spread with Paged Card—is architecturally and visually invalid in a unified document scroll container and is deliberately excluded.)*

2. **Visual Indicators (Multi-Surface Transparency)**:
   - **Deck Subtitle (Bottom Border)**: Replace the current binary `spread` tag with an explicit tri-state badge:
     - State 1: `spread` (dim)
     - State 2: `card-spread` (dim)
     - State 3: `paged` (dim)
   - **Deck Title (Top Border)**: When in State 1 (Fully Spread), replace the misleading active tab counter (e.g., `3/3`) with an explicit `all 3` or `spread 3` chip to clearly signal card concatenation.
   - **Block Rail (Timeline)**: In the right-hand key hint area, explicitly distinguish navigation semantics:
     - Block-Paged: `[ / ] page` (accompanied by page badge `⧉`).
     - Block-Spread: `[ / ] scroll` (accompanied by continuous flow badge `≡`).
   - **Transient Feedback**: Emit a brief TUI notification toast upon toggle (`self.notify("Deck view: Paged deck, spread card")`).

3. **Keymap Ergonomics**:
   - **Primary Shortcut**: **`P`** (`Shift+p`) bound to `cycle_deck_card_view`.
     - **Why `P`**: Completely unbound at the `app:` level in `default_config.yml`. It forms an intuitive, memorable pair with lowercase `p` (`pick_deck`): `p` picks the deck, `P` toggles the deck's presentation mode. It is 100% terminal/tmux safe (standard ASCII 80) and conflict-free.
     - **Cycle Direction**: Pressing `P` advances forward: $\text{Fully Spread (1)} \to \text{Paged Deck, Spread Card (2)} \to \text{Paged Deck, Paged Card (3)} \to \text{Fully Spread (1)}$.
   - **Secondary / Leader Shortcut**: Add `,s` (mnemonic: leader + spread) under `ace.keymaps.leader_mode.keys.view_mode`.
   - **Deck Picker Modal Integration**: Add a direct presentation toggle key (`Tab` or `s`) within the `p` picker modal.

4. **Anchor & Scroll Preservation**:
   - Seamlessly reuse the hierarchical `ReadingAnchor(card_id, block_id, offset_rows, pinned)` mechanism introduced in `panel_transitions.py` so mode flips never disorient the reader or lose the active reading position.

---

## 2. Research Report Deliverable

The complete, unabridged research document has been written to the research repository and registered as a durable SASE artifact:

- **Absolute Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/deck_and_card_spread_paged_toggle_ux__gem.md`
- **Artifact Reference**: `research:202609/deck_and_card_spread_paged_toggle_ux__gem.md`
- **Registration Command**:
  ```bash
  sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/deck_and_card_spread_paged_toggle_ux__gem.md" -l "research:202609/deck_and_card_spread_paged_toggle_ux__gem.md"
  ```
- **Registration Status**: Exact match verified (`explicit:2912e8cf1d5e48e91006fc94`).
- **Final Declaration**: Submitted and accepted via `sase final submit` (`Accepted final declaration for: commit`).
