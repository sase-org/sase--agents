# Chat History - ace-run (research.2p.gem)

- **TIMESTAMP:** 2026-09-26 18:23:51 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2p.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_181206.md`

## Prompt

%id(gem, clan=research.2p)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2p.cdx`, `research.2p.grk`, `research.2p.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add a new
way of grouping agents on the Agents tab using sub-tabs.

- The motivation behind this change is to allow sase to scale up the number of agents
  that the user can manage from a single TUI instance.
- This will be useful, for example, in the case of nodes running on remote machines,
  where I would like them to use a tab that is named after the machine the node is
  running on (agents that are running on the apollo machine should show up on a sub-tab
  named something like "apollo", for example).
- This will require migrating the exisint `[` / `]` keymaps which are used for card
  blocks to `(` / `)` (so we can use the square bracket keys to navigate the new
  sub-tabs on the "Agents" tab).
- It's come to my attention that agent clans and agent tribes, just like these new
  sub-tabs, are really just a way of grouping a bunch of nodes together, unlike agent
  sessions, for example, which have a deeper conceptual meaning. I don't think that this
  codebase's logic reflects that. Agent clans in particular have some unique
  requirements that I think we should remove in order to unify the concept of agent
  groups/clusters (this new "agent clusters" term should be added to the glossary) that
  can be moved to and from clans/tribes/tabs in a seamless and intuitive way.
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

# Research & Design Report: Agents Tab Sub-Tabs, Fleet Grouping, Keymap Migration, and Concurrency Architecture Critique

**Author:** Researcher gem (Swarm: `research.2p.*`)  
**Report File:** [`agents_tab_subtabs_and_fleet_grouping__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/agents_tab_subtabs_and_fleet_grouping__gem.md)  
**Registered Artifact:** `research:202609/agents_tab_subtabs_and_fleet_grouping__gem.md` (`file:explicit:d8ad7c849c4df9b7aac0dd97`)  

---

## Executive Summary

As SASE scales from local workstation execution to distributed multi-machine fleets (such as local host `here`, remote server `apollo`, and build host `athena`), managing dozens of concurrently active agents within a single TUI instance becomes an operational bottleneck. 

This research investigates your proposal to:
1. Add sub-tabs on the **Agents** tab to partition agents (specifically by host machine, e.g. a dedicated tab for `apollo`).
2. Migrate card-block stepping keymaps from `[` / `]` to `(` / `)` to free the square bracket keys for sub-tab cycling.
3. Unify **Agent Clans**, **Agent Tribes**, and **Sub-Tabs** under a new glossary concept called **"Agent Clusters"**, removing clan-specific restrictions so nodes can be dynamically moved between clans, tribes, and tabs.

### Summary of Critique and Findings

| Element | Evaluation | Strategic Verdict | Key Justification |
| :--- | :--- | :--- | :--- |
| **Agents Tab Sub-Tabs** | **Strongly Endorsed** | **Adopt** | Solves multi-machine fleet scaling; isolates high-volume remote workloads; provides clear spatial context. |
| **`[` / `]` &rarr; `(` / `)` Keymap Migration** | **Strongly Endorsed** | **Adopt** | Creates universal symmetry with the `Artifacts` tab (where `[` / `]` already cycles sub-tabs). `(` / `)` has zero collisions on the Agents tab. |
| **Dissolving Clans into "Agent Clusters"** | **Critically Flawed** | **Reject** | Conflates **orchestration & synchronization** (Clans) with **taxonomy** (Tribes) and **presentation windowing** (Sub-tabs). |
| **Dynamic Inter-Clan Node Movement** | **Critically Flawed** | **Reject** | Destroys `@clan:<name>` wait dependency resolution, generational tracking, Rust core schema contracts, and lexical namespace integrity. |
| **"Agent Clusters" Glossary Term** | **Unnecessary & Ambiguous** | **Reject / Limit to UI** | Degrades SASE's precision. SASE already has exact concepts for every tier. If retained at all, it should only refer to presentation row clusters. |

---

## 1. Deep Critique: The Four Orthogonal Dimensions of SASE

Your intuition that agent organization feels disjointed in places is astute, but concluding that *Agent Clans* are "just a way of grouping nodes together like sub-tabs" is an architectural category error. SASE organizes agents across four strictly orthogonal dimensions:

```
+---------------------------------------------------------------------------------------+
|                               FOUR ORTHOGONAL DIMENSIONS                              |
+---------------------------------------------------------------------------------------+
| 1. TEMPORAL (Lifecycle)      | Agent Session   | Strictly sequential turn handoffs     |
| 2. CONCURRENCY (Execution)   | Agent Clan      | Parallel swarm with wait resolution  |
| 3. TAXONOMIC (Metadata)      | Agent Tribe     | User-facing classification tag       |
| 4. PRESENTATION (Viewport)   | Sub-Tabs/Panels | Client-side TUI projection & filter  |
+---------------------------------------------------------------------------------------+
```

### Why Agent Clans Cannot Be Dissolved into Mutable "Clusters"

1. **Wait Dependency Resolution (`@clan:<name>`):**
   - In [`src/sase/core/wait_dependency_resolution`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/core/wait_dependency_resolution/_index_queries.py), workflows, chops, and dependent agents wait for clan completion. SASE evaluates completion as the **aggregate success of all members of that clan generation**.
   - If nodes could be dynamically moved into or out of clans at runtime, wait barriers would become non-deterministic race conditions: when does a clan complete if its membership is mutable?
2. **Generations and Rust Core Backend Contract:**
   - Under [Core Memory Rule 1.3](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/AGENTS.md), shared domain state belongs in the `sase-core` Rust crate. Clans maintain durable on-disk state under `<sase_home>/agent_clans/<clan>.json` managed by `sase_core_rs` ([`src/sase/core/agent_clan_record.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/core/agent_clan_record.py)). Clans track generations, summary scripts (`sase_clan_summary_epic.py`), and machine locks.
3. **Lexical Namespace & Workspace Invariants:**
   - All clan members are strictly scoped by hood: `<clan>.<suffix>`. Moving an agent between clans would require renaming running processes, migrating ephemeral workspaces, and breaking git branch tracking.
4. **Agent Tribes Already Provide Mutable Tagging:**
   - SASE already has a concept for user-defined categorization: **Agent Tribes** (`@<tribe>`). Unlike clans, tribes are pure metadata and **can already be dynamically reassigned post-launch** with `sase agent tribe`.

**Recommendation on Glossary:** Do **not** add "Agent Clusters" as an orchestration primitive. Preserve the crisp separation between **Sessions** (sequential chains), **Clans** (parallel swarms with wait barriers), **Tribes** (categorical tags), and **Sub-Tabs** (UI viewports).

---

## 2. Design: Machine-Driven Fleet Sub-Tabs on the Agents Tab

### 2.1 The Visual Layout

Sub-tabs on the Agents tab should represent **Machine Topology**, providing a clean horizontal axis of control:

```
+----------------------------------------------------------------------------------------------------+
|  AGENTS  │  Artifacts  │  Services                                             ● apollo  ● athena  |
+----------------------------------------------------------------------------------------------------+
|  [1] here  │  [2] apollo (12 ●)  │  [3] athena (4 ▲)  │  [0] all (21)                              |
+----------------------------------------------------------------------------------------------------+
|  @default                                    │  apollo.build-worker-3                               |
|    here.compiler-fix (running)               │  Deck: [Main]  Files  Tools                         |
|    here.test-runner (done)                   │  +------------------------------------------------+ |
|                                              │  | Output (Spread)                                | |
|                                              │  | ---------------------------------------------- | |
|                                              │  | Compiling sase_core v0.8.2...                  | |
|                                              │  | Finished dev [unoptimized + debuginfo]         | |
|                                              │  +------------------------------------------------+ |
|                                              │                                                     |
|                                              │  ( ) card-block  [ ] subtab  p pick-deck  P toggle  |
+----------------------------------------------------------------------------------------------------+
| %dispatch(apollo) > _                                                                              |
+----------------------------------------------------------------------------------------------------+
```

### 2.2 Core Design Highlights

1. **Re-use `PanelTabStrip`:**
   - Integrate SASE's standard, highly polished [`PanelTabStrip`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/ace/tui/widgets/panel_tab_strip.py) into `agents-header` directly below `agents-filter-bar`.
   - Supports digit shortcuts (`1`, `2`, `3`, `0`), uppercase active indicators, and reflow-to-fit.
2. **Dynamic Machine Enrollment:**
   - Tabs are dynamically built from [`src/sase/dispatch/machine_catalog.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/dispatch/machine_catalog.py): `here` (local), enrolled remote machines (`apollo`, `athena`), and `all` (unified fleet view).
   - Remote tabs display live health pills (`●` green/connected, `▲` amber/alert).
3. **Contextual Dispatch Coupling:**
   - When focused on `[2] apollo`, typing an instruction in the prompt area automatically prefills/hints `%dispatch(apollo)`, eliminating the friction of manual target tagging.
4. **Independent Selection & Highlight Memory:**
   - Switching between `here` and `apollo` preserves each tab's cursor position using [`restore_selection_by_identity()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/ace/tui/util/selection.py).
5. **Adherence to `tui_perf.md`:**
   - Sub-tab switching operates as an in-memory fast-path filter (`_refilter_agents()`) over the warm fleet cache; it never triggers network fetches or full list remounts.

---

## 3. Keymap Ergonomics & Migration Plan

### 3.1 Unifying `[` / `]` for Universal Sub-Tab Cycling

On the **Artifacts** tab, `[` and `]` already cycle sub-tabs (`cycle_artifacts_subtab`). Reallocating `[` and `]` on the **Agents** tab to cycle `here` &rarr; `apollo` &rarr; `athena` &rarr; `all` establishes **100% universal keymap symmetry** across the entire application.

### 3.2 Migrating Card Blocks to `(` / `)`

In [`src/sase/default_config.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/src/sase/default_config.yml):
```yaml
    app:
      # Sub-tab switching (Universal across Agents and Artifacts)
      cycle_agents_subtab: "right_square_bracket"
      cycle_agents_subtab_reverse: "left_square_bracket"
      cycle_artifacts_subtab: "right_square_bracket"
      cycle_artifacts_subtab_reverse: "left_square_bracket"

      # Card-block stepping (Reply card multi-turn blocks)
      # Shares ( / ) with files_version (Artifacts); disambiguated by tab availability.
      next_card_block: "right_parenthesis"
      prev_card_block: "left_parenthesis"
```

- **Zero Collisions:** `(` and `)` (`left_parenthesis` / `right_parenthesis`) are only used for `files_prev_version` / `files_next_version` on the Artifacts &rarr; Files pane. Tab availability gating completely isolates them.
- **Ergonomic Frequency Alignment:** Unshifted `[` / `]` is reserved for high-frequency viewport switching, while shifted `(` / `)` is allocated to fine-grained inspection of historical reply blocks.

---

## 4. Adjusted Requirements Matrix

| Initial Proposal | Identified Risk | Recommended Adjustment | Benefit |
| :--- | :--- | :--- | :--- |
| **Unify clans, tribes, and tabs into "clusters"** | Conflates concurrency/waits with UI presentation; breaks Rust core backend contracts. | **Reject unification.** Retain crisp separation between Clans (concurrency), Tribes (tags), and Sub-tabs (presentation). | Prevents scheduling deadlocks and maintains system integrity. |
| **Move nodes between clans dynamically** | Non-deterministic wait barriers; breaks lexical hood `<clan>.<member>`. | **Disallow dynamic clan mutation.** Support dynamic movement only between **Tribes** (`sase agent tribe`) and **Sub-tabs** (UI filtering). | Guarantees deterministic workflow completion and reliable artifact indexing. |
| **Add "agent clusters" to glossary** | Creates ambiguous vocabulary. | **Do not add to glossary.** Keep terms strictly defined around Session, Clan, Tribe, and Hood. | Maintains architectural clarity. |
| **Sub-tabs on Agents tab** | Unspecified grouping criteria. | **Standardize on Machine Topology Sub-Tabs (`here`, `apollo`, `all`).** | Solves the primary scaling motivation. |
| **Migrate `[` / `]` to `(` / `)`** | None. | **Adopt exactly as proposed.** | Achieves seamless UI consistency across all tabs. |

---

## 5. Artifact Verification & Next Steps

1. **Research Report Written:** [`sase/repos/research/202609/agents_tab_subtabs_and_fleet_grouping__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/agents_tab_subtabs_and_fleet_grouping__gem.md)
2. **Durable Snapshot Registered:**
   ```bash
   sase artifact create -p "/home/bryan/.../agents_tab_subtabs_and_fleet_grouping__gem.md" -l "research:202609/agents_tab_subtabs_and_fleet_grouping__gem.md"
   # Result: file:explicit:d8ad7c849c4df9b7aac0dd97
   ```
3. **Turn Finalizer Declared:** SASE final declaration committed successfully via `sase final submit`.

The complete architectural research report is ready in the research repository for review and synthesis by the lead researcher.
