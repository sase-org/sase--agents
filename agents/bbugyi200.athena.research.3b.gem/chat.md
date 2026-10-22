# Chat History - ace-run (research.3b.gem)

- **TIMESTAMP:** 2026-10-02 08:30:49 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3b.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_082005.md`

## Prompt

%id(gem, clan=research.3b)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3b.cdx`, `research.3b.cld`, `research.3b.grk`, `research.3b.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to
improve the "Agents" tab deck panel and the sase pager's split view support (see the
sase-1eg epic bead for context on the latter).

- We currently only support two views, each of which support just two panes: horizontal
  and vertical.
- I want to add a support for two additional views that each use three panes. Namely:
  - A horizontal split 3-pane view should be triggered when the `|` keymap is used if a
    horizontal split is already shown by splitting the currently focused pane
    vertically. Pressing `|` again should switch to the 3-pane view described in the
    bullet below. Alternatively, pressing `\` closes the larger horizontal pane which
    switches us to the 2-pane vertical view.
  - A vertical split 3-pane view should be triggered when the `\` keymap is used if a
    vertical split is already shown by splitting the currently focused pane
    horizontally. Pressing `\` again should switch to the 3-pane view described in the
    bullet above. Alternatively, pressing `|` closes the larger vertical pane which
    switches us to the 2-pane horizontal view.
- The `<ctrl+b>` keymap should be added that worked like the `<ctrl+f>` keymap (i.e.
  changes which pane is focused) but in the reverse direction.
- The new `<ctrl+shift+b/f>` keymaps should be added to give the user the ability to
  swap the current pane with the previous/next pane.
- A new `<ctrl+shift+d>` keymap should be added that deletes the current pane. This
  keymap should only be active when at least two panes are visible. We should still
  support switching back to a single-pane view when the `\` keymap is used but the
  2-pane horizontal view is already active or when the `|` keymap is used but the 2-pane
  vertical view is already active.
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

# Research Summary: 3-Pane Split View Architecture for the Agents Deck Panel & SASE Pager

**Report Location:** [`three_pane_deck_and_pager_split_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/three_pane_deck_and_pager_split_architecture__gem.md)  
**Registered Artifact:** `research:202610/three_pane_deck_and_pager_split_architecture__gem.md` (`ref: file:explicit:f7e83c838acd374544106c90`)  
**Researcher:** `research.3b.gem`

---

## 1. Executive Verdict & Critique: Is This a Good Idea?

### The Good: High Practical Utility
**Yes, the end-state capability is an outstanding improvement.**
- **In the Agents Tab:** A 3-pane layout transforms triage efficiency. SASE agents operate across four primary deck surfaces: `MAIN` (prompt/replies), `FILES` (touched files/diffs), `TOOLS` (runs and LLM calls), and `FINAL` (finalizer declarations). In 2-pane mode, triage requires constant deck-cycling. A 3-pane layout enables a simultaneous **"Triage Triad"** (`MAIN` + `FILES` + `TOOLS`), giving immediate situational awareness without keystroke thrashing.
- **In the SASE Pager:** 3 panes allow side-by-side reading of historical revisions (past version vs. current version) alongside a spec, bead, or code document.

### The Critique: Flaws in the Proposed State Machine
While the *capability* is excellent, the specific *keymap state machine* proposed contains critical usability and architectural flaws:

1. **Destruction of 2-Pane Rotation:**
   In SASE today (`docs/pager.md`, `decks/layout.py`), pressing the opposite split key (`|` in horizontal, `\` in vertical) smoothly rotates the orientation between 2 panes. Overloading `|` to spawn a 3rd pane breaks this muscle memory and requires a clumsy two-step key dance (`|` then `\`) to rotate orientations.
2. **Inversion of Key Affordances:**
   The proposal specifies that in a 3-pane horizontal view, pressing `\` (the horizontal key) closes the larger pane and switches to a 2-pane *vertical* view. Using a horizontal key to produce a vertical layout violates visual affordance principles.
3. **Focus-Blind Destructive Deletion:**
   Automatically closing "the larger pane" via `\` or `|` destroys content regardless of whether the user was actively reading it. Destructive actions should never be triggered by layout navigation keys.
4. **Geometric Topologies (The 4 vs. 2 Problem):**
   Splitting the "focused pane" creates **four** distinct layout topologies (Top-split, Bottom-split, Left-split, Right-split), not two. Unambiguous transitions require formalizing a Master-Stack hierarchy.
5. **Terminal Extents:**
   With SASE's minimum reading constraints (`MIN_STACKED_PANE_HEIGHT = 7`, `MIN_BESIDE_PANE_WIDTH = 32`), 3 panes requires at least 80 columns by 20 rows. Sizing guards must refuse gracefully when terminal dimensions are insufficient.

---

## 2. Keymap Analysis & Collision Findings

- **`<ctrl+b>` (Focus Previous Pane):**  
  Excellent, intuitive complement to `<ctrl+f>`. In ACE, `ctrl+b` is currently mapped to `scroll_prompt_up` when unsplit; when split, it routes to `toggle_deck_focus_reverse` (matching `ctrl+f`). In Pager, `ctrl+b` is completely free.
- **`<ctrl+shift+b>` & `<ctrl+shift+f>` (Swap Panes):**  
  High-utility capability for promoting secondary stack panes to the master reading position. Terminal safety notes: Provide modal fallbacks (`ctrl+w x` in Pager, leader mode in ACE) for environments where terminals intercept Ctrl+Shift+F.
- **`<ctrl+shift+d>` (Delete Current Pane):**  
  **Codebase collision identified:** `src/sase/ace/tui/bindings.py:306` conditionally binds `ctrl+shift+d` to `debug_leak_snapshot` when `SASE_ACE_DEBUG_LEAKS=1`.  
  *Fix:* Rebind the developer leak probe to `ctrl+shift+alt+d` or ensure `action_delete_deck_panel` takes binding precedence. Deleting the *focused* pane smoothly collapses 3 panes $\to$ 2 panes $\to$ 1 pane.

---

## 3. Recommended Solution: Master-Stack Tiling

```text
===================================================================
                   RECOMMENDED 3-PANE TOPOLOGIES
===================================================================
          MAIN_HORIZONTAL                     MAIN_VERTICAL
+---------------------------------+  +---------------+------------+
|                                 |  |               |  Stack 1   |
|         MASTER PANE             |  |               |  (Pane 1)  |
|          (Pane 0)               |  |  MASTER PANE  +------------+
|                                 |  |   (Pane 0)    |  Stack 2   |
+----------------+----------------+  |               |  (Pane 2)  |
|  Stack 1       |  Stack 2       |  |               |            |
|  (Pane 1)      |  (Pane 2)      |  +---------------+------------+
+----------------+----------------+
===================================================================
```

### Transition Model
1. **Constructive Layout Keys (`\`, `|`):**
   - From `SINGLE`: `\` opens `TOP_BOTTOM`; `|` opens `LEFT_RIGHT`.
   - From 2-Pane: Pressing the same key unsplits; pressing the opposite key rotates orientation (preserving 2-pane rotation). Pressing split on an already split layout advances to 3-pane (`MAIN_HORIZONTAL` or `MAIN_VERTICAL`).
   - In 3-Pane: `\` and `|` rotate between `MAIN_HORIZONTAL` and `MAIN_VERTICAL`.
2. **Destructive Operations (`<ctrl+shift+d>`):**
   - Layout keys *never* delete panes.
   - `<ctrl+shift+d>` deletes the **currently focused** pane. If Master is deleted, Stack panes expand to occupy the display. If a Stack pane is deleted, the layout degrades cleanly to 2 panes.
3. **ACE Widget Composition via CSS Grid:**
   - Pre-compose 3 `DeckPanel` instances (`agent-deck-panel-0`, `1`, `2`) inside `DeckArea`.
   - Use Textual's native CSS Grid (`grid-size: 2 2`, `column-span: 2` / `row-span: 2`) in `styles.tcss` for high performance, zero container nesting, and seamless scroll preservation.
   - `choose_new_panel` automatically selects `TOOLS` (or `FINAL`) for Panel 2, instantly assembling the Triage Triad.
4. **Pager Focus Discipline:**
   - Enforce that *only the focused pane paints link label badges* to eliminate character collision and ensure single-key link jumping remains deterministic.

---

## 4. Verification & Artifact Registration

- The detailed analysis has been written to:  
  [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/three_pane_deck_and_pager_split_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/three_pane_deck_and_pager_split_architecture__gem.md)
- Snapshot registered:  
  `sase artifact create -p "/home/bryan/.../three_pane_deck_and_pager_split_architecture__gem.md" -l "research:202610/three_pane_deck_and_pager_split_architecture__gem.md"`  
  *(Ref: `file:explicit:f7e83c838acd374544106c90`)*
- SASE finalizer declaration submitted and accepted (`Accepted final declaration for: commit`).
