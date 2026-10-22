# Chat History - ace-run (research.4a.gem)

- **TIMESTAMP:** 2026-10-12 07:56:51 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4a.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261012_074540.md`

## Prompt

%id(gem, clan=research.4a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4a.cdx`, `research.4a.cld`, `research.4a.grk`, `research.4a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to make decisions look much better in the gate panels shown by the TUI.
Currently, not only does it look bad, but some of the text related to some decisions
gets cut off. See the ~/tmp/screenshots/20261012_074036.png screenshot for an example of
what these look like now. Can you do some research with the goal of helping me come up
with the best possible TUI design for this? End your analysis with a recommended
solution and UX. 
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

# Research Report: TUI Gate Panel Decisions Redesign & UX

**Investigator:** Researcher `gem` (`research.4a.gem`)  
**Deliverable File:** [`tui_gate_panel_decisions_redesign__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/tui_gate_panel_decisions_redesign__gem.md)  
**Registered Artifact:** `file:explicit:dd52f5d40b0f2620a5f0ca02` (`research:202610/tui_gate_panel_decisions_redesign__gem.md`)

---

## 1. Forensic Analysis of Current Implementation & Screenshot

Inspection of [`20261012_074036.png`](file:///home/bryan/tmp/screenshots/20261012_074036.png) alongside the Textual implementation across [`PlanApprovalModal`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_approval_modal.py), [`PlanDecisionRows`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_decision_rows.py), and [`styles.tcss`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/styles.tcss) pinpoints four interacting root causes:

1. **Fixed-Width Left Rail Bottleneck:**
   - In [`styles.tcss`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/styles.tcss#L1779-L1781), `.gate-review-actions--decisions` is hardcoded to `width: 50;`.
   - Subtracting 2 border cells and 2 padding cells leaves an interior printable width of only **46 columns**.
2. **Gross Screen Real-Estate Imbalance:**
   - In standard terminals (~180–220 columns), the 50-cell left rail takes only ~25% of the width, while the right document pane (`.gate-review-document`) takes ~140–160 columns (`width: 1fr`).
   - Because standard Markdown prose wraps at 80–90 columns, **over 60 columns on the right are wasted as dead black space**, while the critical decisions interface starves in 46 columns.
3. **Widget Misuse & Truncation Mismatch:**
   - In [`plan_decision_rows.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_decision_rows.py#L328-L332), each row is mounted as a monolithic Textual `Button` widget. Textual buttons clip overflowing labels horizontally (`overflow: hidden; text-overflow: clip`) rather than wrapping.
   - Python code in `_collapsed_row_text` explicitly truncated at 80/60 characters—assuming a wide screen—so truncation occurs *off-screen*, resulting in Textual violently clipping text mid-word at column 42 (e.g., `"Where should the relocated legacy tree (f"`, `"Should the ~70 stow-style dotfile symlink"`).
4. **Vertical Choking (`max-height: 16`):**
   - In [`styles.tcss`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/styles.tcss#L1783-L1786), `.plan-decision-rows` is restricted to `max-height: 16`.
   - With 1 expanded decision (taking ~7 lines) and 3 collapsed decisions (taking ~2–3 lines each), total required height exceeds 16 lines. In the screenshot, **Decision 4 (`old_tmp`) is completely invisible and pushed off-screen**, appearing only in the tiny bottom verdict summary.

---

## 2. Evaluation of Architectural Design Directions

| Design Alternative | Geometry & Behavior | Pros | Cons | Verdict |
| :--- | :--- | :--- | :--- | :--- |
| **A. Proportional Two-Pane with Decision Cards** | Widen rail to **74 cols** (or 38–40%); replace `Button` with multi-line `PlanDecisionCard` + 1-line collapsed pills. | Zero text clipping; comfortable 70-col text measure; preserves 100+ cols for `plan.md`; minimal implementation risk. | Rail consumes slightly more screen space. | **Recommended** |
| **B. Three-Pane Split** | Left Nav (26 cols) + Center Inspector (58 cols) + Right Plan (1fr). | Cleanly separates index from detail inspection. | Cramped on terminals <150 cols; high refactoring complexity. | Viable for ultrawide, but heavy. |
| **C. Top Drawer / Header Carousel** | Top decisions panel (30% height) + Bottom plan document (70% height). | Maximizes horizontal width. | Destroys scarce vertical terminal height; plan requires constant scrolling. | Rejected |
| **D. Inline Document Decisions** | Interactive forms embedded inside `plan.md` at callout positions. | Contextual inline placement. | Fragmented review across 500 lines of plan; complex focus management. | Rejected |

---

## 3. Recommended Solution & UX Specification

### A. Responsive Rail Geometry & Sizing
Update [`styles.tcss`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/styles.tcss) to use a responsive, generous column width:
- **Wide Screens (>=140 cols):** Expand `.gate-review-actions--decisions` to `width: 74; max-width: 42%;`. Inside 74 columns (70 printable), indented option descriptions have **64 characters of wrapping width**—the typographical sweet spot for reading English prose.
- **Medium Screens (100–139 cols):** Responsive fallback to `width: 62;`.
- **Narrow Screens (<100 cols):** Existing bottom dock mode (`-gate-review-narrow`) handles tight spaces.
- **Remove `max-height: 16`:** Increase `.plan-decision-rows` to `max-height: 28; height: auto; scrollbar-gutter: stable;` so all decisions fit without artificial height clipping.

### B. Widget Architecture: `PlanDecisionCard` & Accordion
Replace the Textual `Button` in [`plan_decision_rows.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_decision_rows.py) with a composite component:
1. **Expanded Card (Focused):**
   - **Card Header:** Frame with index and ID (`[1/4] root`) plus a status chip (`● MODIFIED` in gold `#FFD700` or `★ DEFAULT` in dim cyan).
   - **Wrapped Question Body:** `Static` widget with `text-wrap: wrap`, displaying the full prompt question in high-contrast text.
   - **Formatted Option List:** Radio glyphs (`◉`/`○`), bold key, `★ default` marker, and cleanly wrapped consequence descriptions on the subsequent line.
   - **Dedicated Rationale Box:** Distinct styled container with `border: round $surface-light` for the author's `why`.
   - **Memory Provenance Section:** Badges for note selectors, quote preview, and high-visibility amber warning badges for unverified memory claims.
2. **Compact Collapsed Pills (Inactive):**
   - Inactive decisions collapse into a **single line**:
     `○ 2. dotfiles     repoint ★  Should ~70 stow-style dotfile links...`
   - In a 4-decision review, 3 collapsed pills consume only 3 vertical lines. The active card has ~15 lines to breathe, ensuring **all decisions remain visible simultaneously**.

### C. Keyboard & Interaction Ergonomics
Preserve and reinforce vim-style review controls in [`plan_approval_modal_controls.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_approval_modal_controls.py):
- `j` / `k` (or `Down` / `Up`): Move between decisions; automatically expands the focused card, collapses the previous, and triggers [`_scroll_to_focused_decision()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/plan_approval_modal_view.py#L234-L260) to scroll `plan.md` to the corresponding `> [!decision]` callout.
- `h` / `l` (or `Left` / `Right`): Step through choices for the active decision. Re-tints the plan callout in real time.
- `Space`: Quick-toggle for boolean options or step to next choice.
- `1`–`9`: Direct numeric option selection for the focused decision.
- `r` / `R`: Reset current decision / reset all decisions to default.
- `Enter` / `Ctrl+S`: Submit approved verdict with selected decision inputs.

---

## 4. Deliverable and Artifact Registration

- **Research Report File:** [`tui_gate_panel_decisions_redesign__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/tui_gate_panel_decisions_redesign__gem.md)
- **Artifact Ref:** `file:explicit:dd52f5d40b0f2620a5f0ca02`
- **Label:** `research:202610/tui_gate_panel_decisions_redesign__gem.md`
- **Host Finalizer Declaration:** Completed via `sase final submit` (obligated commit for `sdd:research`).
