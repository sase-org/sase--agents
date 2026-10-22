# Chat History - ace-run (research.52.gem)

- **TIMESTAMP:** 2026-10-19 15:39:04 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.52.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_152246.md`

## Prompt

%id(gem, clan=research.52)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.52.cdx`, `research.52.cld`, `research.52.grk`, `research.52.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make it much clearer whether or not a user can scroll down to see the entirety
of the currently focused sase agent deck (which they can only do when the cards are not
split out to sub-tabs).

- I was thinking that we could achieve this by only showing card sub-tabs when we
  actually have split out sub-tabs (i.e. when the user has to use the `<ctrl+j/k>`
  keymaps to view other cards in the current deck).
- We could also start showing a bright and clearly visible set of badges that indicate
  the view.
- As a part of this change, I was also thinking that we stop showing "auto" and "fixed"
  and start representing this state using a little lock icon instead?
- Think hard about what the best possible UX is here (I might have gotten a few things
  wrong).

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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: Deck Scroll Clarity, Sub-Tab Affordances, and View Badges UX Architecture

- **Author**: Researcher `research.52.gem` (Gemini 3.8 Flash)
- **Report File**: [`deck_scroll_clarity_and_view_badge_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/deck_scroll_clarity_and_view_badge_ux__gem.md)
- **Artifact Snapshot**: Registered as `research:202610/deck_scroll_clarity_and_view_badge_ux__gem.md` (`explicit:c604d545b61ea5be9d70e44f`)

---

## Executive Summary & Plan Critique

The user's core intuition is **fundamentally sound and directly targets the root cause of the confusion**:

### Why Users Are Confused Today
In `src/sase/ace/tui/widgets/decks/titles.py`, both `spread` mode (where all cards are vertically concatenated in one continuous scroll stream) and `paged` mode (where only one card is mounted at a time) render an almost identical horizontal tab strip:
```text
Spread: ◆ MAIN  spread · auto  ┃  Prompt │ Context │ Reply  1/3
Paged:  ◆ MAIN  cards · auto   ┃ [Prompt]│ Context │ Reply  1/3
```
In GUI/TUI interface design, horizontal tabs with an active highlight universally communicate **mutually exclusive view states**. When users see `[Prompt] │ Context │ Reply`, their subconscious mental model insists: *"I am on tab 1; scrolling down will not reveal tab 2; I must switch tabs."* In spread mode, this is a **false affordance**. 

Furthermore:
1. **The current badge lacks visual salience**: `view_badge.py` styles the badge with transparent background and muted grey joiners (`#888888`), causing it to blend into the border label.
2. **"Cards" is misleading terminology**: A deck is composed of cards in *both* modes; calling paged mode `cards` fails to describe the layout.
3. **"Auto" vs "Fixed" is internal engine mechanics**: Users need to know *what navigation affordances they have right now*, not what algorithm resolved the layout.

---

## Detailed Critique of Proposed Adjustments

### 1. Showing Card Sub-Tabs Only When Actually Paged
- **Verdict**: **Strongly Recommended (with one critical refinement)**.
- **Why it works**: Eliminates the false affordance. When sub-tabs are visible, they mean: *"You must use `<Ctrl+J/K>` to switch pages."* When sub-tabs are absent, it means: *"The entire deck is a continuous document; scroll down freely."*
- **The "Below-the-Fold" Discovery Blind Spot**: If a long `Prompt` card fills the terminal viewport, and all sub-tabs are hidden, the user cannot see `Context` or `Reply` below the fold and might assume the deck contains only a Prompt.
- **Recommended Refinement**: In spread mode, replace the sub-tabs with an **informational Reading Anchor / Card Count** rather than leaving empty space:
  ```text
  Spread: ◆ MAIN  [ SPREAD ] ┃ (3 cards · scroll ↕)
  ```
  As the user scrolls down past `━━ ◆ Context ━━━━`, the title bar smoothly tracks: `§ Context (2/3)`. This provides reading orientation without looking like interactive tabs.

### 2. High-Contrast View Badges
- **Verdict**: **Strongly Recommended**.
- **Visual Styling**: Use **inverted theme pill chips** (similar to SASE's reverse-gold `ZOOM` chip: `bold #1a1a1a on <color>`):
  - `SPREAD`: Cyan / Theme Secondary background pill: `[ SPREAD ]` (continuous document flow).
  - `PAGED`: Amber / Warning background pill: `[ PAGED ]` (segmented / partitioned pages).
  - `BLOCKS`: Purple / Violet background pill: `[ BLOCKS ]` (card blocks paged).
- **Terminology**: Replace the ambiguous label `cards` with `PAGED`. Never use `cards` to describe a layout mode.

### 3. Replacing "Auto" and "Fixed" with a Lock Icon (`🔒`)
- **Verdict**: **Strongly Recommended (Adopt the "Quiet Default" Pattern)**.
- **Why it works**:
  - Saves 5–8 horizontal cells in the title bar (vital for narrow 2-pane and 3-pane split layouts where widths drop to 40–50 columns).
  - `🔒` is universally recognized as "pinned / locked by user preference".
  - SASE already standardizes on `🔒` in other TUI modules (`bead_note_modal`, `_prompt_input_bar_title`).
- **Critical Refinement (Quiet Default)**:
  - Do **NOT** show an open lock `🔓` for `auto`. An open lock adds visual clutter.
  - When `AUTO`: Show the badge alone (`[ SPREAD ]` or `[ PAGED ]`).
  - When `FIXED`: Append the lock icon (`[ SPREAD ] 🔒` or `[ PAGED ] 🔒`).
  - For `PENDING` and `BLOCKED` states (e.g. Files media), display `[ SPREAD… ]` or `[ PAGED ] ⚠`.

### 4. Contextualizing Footer Keybinding Hints
Currently, `_keybinding_bindings_agents.py` hardcodes `^J/^K cards` in both modes.
- In **Paged Mode**: `<Ctrl+J/K>` pages between cards. Display: `^J/^K cards` (or `^J/^K tabs`).
- In **Spread Mode**: `<Ctrl+J/K>` performs an anchor jump between card separators. Display: `^J/^K jump` (or `^J/^K section`).

---

## Visual Comparison (Before vs. After)

### Before (Status Quo)
```text
Spread: ┌─ ◆ MAIN  spread · auto ┃  Prompt │ Context │ Reply  1/3 ──┐  <-- Looks like tabs!
Paged:  ┌─ ◆ MAIN  cards · auto  ┃ [Prompt]│ Context │ Reply  1/3 ──┐  <-- Looks identical!
```

### After (Recommended Design)
```text
Spread: ┌─ ◆ MAIN  [ SPREAD ] ┃ 3 cards · scroll ↕ ───────────────────┐  <-- Unambiguously scrollable
Paged:  ┌─ ◆ MAIN  [ PAGED ] 🔒 ┃ [Prompt] │ Context │ Reply  1/3 ────┐  <-- Clear pagination & lock
```

---

## Implementation Roadmap

1. **Phase 1: Badge Renaming & Lock Icon (`src/sase/ace/tui/widgets/decks/view_badge.py`)**:
   - Update string mappings: `SPREAD`, `PAGED`, `BLOCKS`.
   - Remove `· auto` / `· fixed` text; append `🔒` when `resolved.policy is not DeckView.AUTO`.
   - Apply high-contrast inverted pill styles (`bold #1a1a1a on #87D7AF`, `bold #1a1a1a on #D7AF5F`).
2. **Phase 2: Tab Suppression & Spread Anchor (`src/sase/ace/tui/widgets/decks/titles.py`)**:
   - Pass `is_spread` to `deck_title()`.
   - When `is_spread=True`, omit `CardTab` delimiters (`│`) and active-tab pill; display `(N cards · scroll ↕)` instead.
   - When `is_spread=False`, render full sub-tabs.
3. **Phase 3: Footer Hint Alignment (`src/sase/ace/tui/widgets/_keybinding_bindings_agents.py`)**:
   - Dynamically label `<Ctrl+J/K>` as `jump` in spread mode vs `cards` in paged mode.

The complete report has been registered into the durable research artifacts catalog at `research:202610/deck_scroll_clarity_and_view_badge_ux__gem.md`.
