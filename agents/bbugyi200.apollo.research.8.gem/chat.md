# Chat History - ace-run (research.8.gem)

- **TIMESTAMP:** 2026-09-25 09:34:14 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.8.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_092521.md`

## Prompt

%id(gem, clan=research.8)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.8.cdx`, `research.8.cld`, `research.8.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add a new `"` keymap
to the "Agents" tab that opens a new panel which makes it very easy to navigate to any
node, regardless of whether or not it is show. We should be able to jump to hidden agent
session shells and hidden agent clan members, for example. Don't include agent shell
Bash/Python steps.

- This panel should have similar (but more powerful) functionality to the panel that is
  triggered by the backtick keymap in that hints will always be rendered next to nodes
  that the user can jump to by pressing the corresponding keys.
- This functionality will be more powerful in that we will support filtering the list
  (by node name) via a query input bar at the top of the panel.
- By default, the query input bar should not be selected (so the user can press hint
  keys). The `<tab>` keymap should be able to be used to focus the query input bar and
  then unfocus it again to press hint keys.
- The user should also be able to use the `<enter>` keymap to select (and jump to) the
  currently selected node.
- This panel should be large so we can show a good (but fast) preview of the currently
  selected node
- The user should be able to cycle through the nodes listed in the panel using the
  `<ctrl+n/p>` keymaps.
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

# Architectural Research & Design: Agents Tab Omni-Node Jump Panel (`"`)

**Researcher:** `research.8.gem` (Gemini 3.8 Flash)  
**Report Artifact:** [`research:202609/agents_tab_omni_jump_panel__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202609/agents_tab_omni_jump_panel__gem.md)  
**Durable Snapshot Reference:** `file:explicit:8429e5058a5343fec7b985a8`  
**Stored Artifact Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260925092525/agents_tab_omni_jump_panel__gem-801712c5e30f.md`

---

## Executive Summary & Plan Critique

### 1. Is this a good idea?
**Yes, strongly endorsed.**
As SASE workflows increasingly rely on multi-agent swarms, clans, and deep sequential sessions (often containing 10–50+ agents), finding and navigating to a specific agent currently requires either:
1. Manually drilling into and expanding multi-level folds with `h`/`l`/`L`/`H`, or
2. Local hint jump (`'`), which only addresses rows currently rendered and visible on screen, or
3. Cross-tab jump (`` ` `` / `JumpAllModal`), which truncates at 50 top-level visible rows, mixes in unrelated tabs, and has no search filtering or node previews.

Adding a dedicated, omni-node navigation panel bound to `"` fills a critical ergonomic gap in fleet and swarm management.

### 2. Keymap Selection (`"`)
- Pairing `"` (`Shift+'`) with `'` creates a natural mental model:
  - `'` (single quote): Jump among *visible* entries on screen.
  - `"` (double quote): Jump among *all* nodes across the entire agent workspace.
- **Implementation Note:** In Textual, `"` triggers `event.key == "quotation_mark"` (or `character == '"'`). `quotation_mark` must be registered in `src/sase/ace/tui/keymaps/key_validation.py` (`_KEY_DISPLAY`) and bound under `agents` keymaps in `src/sase/default_config.yml`.

### 3. Critique & Adjustments to the Interaction Model
1. **Dual-Mode Focus (`[HINT MODE]` vs `[SEARCH MODE]`):**
   - Defaulting to **Hint Mode** on open is the right call for muscle-memory speed. Power users can press `"` followed immediately by a hint letter (e.g. `a`) for an instant 2-keystroke jump.
   - `<tab>` toggles focus into the search bar (`[SEARCH MODE]`), where typing filters the list.
   - **Recommended Adjustment 1 (Vim search entry):** Allow pressing `/` in Hint Mode to also focus the search bar immediately.
   - **Recommended Adjustment 2 (Escape handling):** Pressing `<escape>` while in Search Mode should first unfocus the search bar back to Hint Mode (retaining the filtered results so hint keys can be pressed), while a second `<escape>` dismisses the modal.
   - **Recommended Adjustment 3 (Direct Enter from search):** When the query narrows the list down to 1–2 items, pressing `<enter>` while still typing should immediately jump to the highlighted match without requiring the user to `<tab>` back to hint mode.
   - **Recommended Adjustment 4 (Dynamic Re-hinting):** As the search query filters the node roster, re-allocate adaptive hints over the filtered subset via `build_jump_hint_maps()`. When 40 nodes filter down to 3, hints collapse from two-character prefixes to single keystrokes (`a`, `b`, `c`).

2. **Node Inclusion & Exclusion Boundaries:**
   - **Included:** Standalone root agents, sequential session containers, clan containers, clan members (both shown and folded), session member shells (both shown and folded), and workflow agent steps (`agent.is_workflow_step_child and agent.step_type == "agent"`).
   - **Strictly Excluded (Per Requirement):** Workflow command execution steps (`agent.is_workflow_step_child and agent.step_type in {"bash", "python"}`).
   - **Excluded:** Background verification monitors, approval gates, and durable proc shells (which belong to the Services and Procs tabs).

3. **The Hidden Node Jump Contract & `TARGET_FILTERED` Recovery:**
   - Jumping to a hidden node triggers `reveal_agent_navigation_target(self, plan)` in `src/sase/ace/tui/actions/navigation/_agent_reveal.py`. This safely expands parent clan containers, session containers, group banners, and panels.
   - **Critical Edge Case Discovered:** If the user currently has an active filter applied in the main Agents tab (e.g. `status:running`) and selects an agent with status `DONE`, `reveal_agent_navigation_target` fails with `AgentRevealFailure.TARGET_FILTERED`.
   - **Adjustment:** When `TARGET_FILTERED` occurs during an omni-jump, the jump action must automatically clear/reset the main tab filter (`self.action_clear_filter()`) and re-reveal the target so navigation never silently fails.
   - **Back-Jump Stack:** Pre-jump position must be pushed to `_entry_jump_agents_anchor_stack` so pressing `ctrl+o` returns the user to their prior location.

4. **Fast Preview Architecture (`tui_perf.md` Compliance):**
   - **Tier 1 (Instant Synchronous Metadata, 0 ms):** Render identity, formatted name, clan/session parentage, status chip, model alias, elapsed duration, and bead link directly from in-memory fields on `Agent`.
   - **Tier 2 (Asynchronous Debounced Snippet, 150 ms):** Read prompt preview or live response tail off the event loop via `asyncio.to_thread` with LRU caching, reflowed via `fit_xprompt_preview` with a quote gutter (`▎`). This guarantees scrolling with `<ctrl+n>` / `<ctrl+p>` never stutters (<16 ms).

---

## UI Layout & Aesthetic Blueprint

```
╭────────────────────────────── ✦ Agents Omni-Jump ✦ ──────────────────────────────╮
│  🔍 Search: [ research_gem                               ]  [1/48]  [SEARCH MODE] │
├───────────────────────────────────────┬──────────────────────────────────────────┤
│ HINT  NODE / CLAN HIERARCHY   STATUS  │ PREVIEW: research_gem [RUNNING]          │
├───────────────────────────────────────┼──────────────────────────────────────────┤
│ [ a ] ▾ clan: research        2 run   │ Agent ID:    sase-0814-gem               │
│ [ b ]   ├─ researcher.8.cdx   DONE    │ Clan:        research (generation 1)     │
│ [ c ]   ├─ researcher.8.cld   DONE    │ Role:        Swarm Specialist (gem)      │
│ [ d ]   ├─ researcher.8.mus   DONE    │ Model:       gemini-3.8-flash (xhigh)    │
│ [ e ]   └─ researcher.8.gem  ►RUNNING │ Elapsed:     1m 42s                      │
│                               (hidden)│ Bead:        #2841 (Research node jump)  │
│ [ f ]   standalone_task_worker DONE   │ Path:        sase_18/sase/repos/research │
│ [ g ] ▾ session: refactor_tui 3 shells├──────────────────────────────────────────┤
│ [ h ]   ├─ #1: inspect_css    DONE    │ PROMPT PREVIEW                           │
│ [ i ]   └─ #2: apply_styles   WAITING │ ▎ You are researcher gem in a 4-agent   │
│                                       │ ▎ swarm. Conduct research independently  │
│                                       │ ▎ on adding a new '"' keymap to the      │
│                                       │ ▎ Agents tab...                          │
│                                       │ ▎ ¶ Target: Agents tab Omni-Jump panel   │
╰───────────────────────────────────────┴──────────────────────────────────────────╯
│ [Tab] Toggle Search · [^N/^P] Next/Prev · [Enter] Jump · [a-z] Direct · [Esc] Close│
╰──────────────────────────────────────────────────────────────────────────────────╯
```

---

## Recommended Implementation Roadmap

1. **Phase 1 — Keymap & Core Registration:**
   - Register `"quotation_mark": '"'` in `src/sase/ace/tui/keymaps/key_validation.py`.
   - Add `jump_to_agent_node: "quotation_mark"` in `default_config.yml` and `app_keymaps.py`.
   - Add hidden key binding in `src/sase/ace/tui/bindings.py`.
2. **Phase 2 — Candidate Collector & Filter Engine:**
   - Collect nodes from `self._agents_with_children`.
   - Filter out `agent.is_workflow_step_child and agent.step_type in {"bash", "python"}`.
   - Include collapsed clan members and session member shells, annotating `is_hidden`.
3. **Phase 3 — Dual-Mode Modal (`AgentNodeJumpModal`):**
   - Implement `FilterInput` with `<tab>` / `/` focus toggle and mode badges.
   - Implement dynamic adaptive hint mapping with `build_jump_hint_maps()`.
   - Wire `<ctrl+n>` / `<ctrl+p>` navigation in both modes.
4. **Phase 4 — Two-Tier Fast Preview & Debouncer:**
   - Synchronous metadata card + debounced (150 ms) background text reflow.
5. **Phase 5 — Reveal Engine & Filter Reset Integration:**
   - Dispatch to `prepare_agent_navigation_target` / `reveal_agent_navigation_target`.
   - Add `TARGET_FILTERED` recovery to reset active main tab filters on jump.
   - Push pre-jump position to `_entry_jump_agents_anchor_stack` for `ctrl+o` back navigation.

The complete research report and technical specification have been committed and registered as a durable artifact at [`research:202609/agents_tab_omni_jump_panel__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202609/agents_tab_omni_jump_panel__gem.md).
