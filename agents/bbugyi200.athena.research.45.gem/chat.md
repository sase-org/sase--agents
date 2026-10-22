# Chat History - ace-run (research.45.gem)

- **TIMESTAMP:** 2026-10-08 18:34:28 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.45.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_181607.md`

## Prompt

%id(gem, clan=research.45)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.45.cdx`, `research.45.cld`, `research.45.grk`, `research.45.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
would like to migrate the "Agents" sub-tab of the "Artifacts" tab to the top-level
"Agents" tab somehow, but I'm not really sure how the UX will look or behave. We have
already done some research on this before (see the agent_history_in_agents_tab.md file
in the research sidecar repo for context).

Can you do some research to help flesh out this UX a bit? Make sure this report contains
rich visuals (think hard about the best way to create these). End your analysis with a
summary of your recommended UX. 
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

# UX Specification: Migrating Artifacts ▸ Agent to the Top-Level Agents Tab

**Researcher:** `research.45.gem`  
**Topic:** UX Architecture, Interaction Models, and Visual Design for Agent History in the Agents Tab  
**Registered Artifact:** [`research:202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md)  
**Accompanying Visual Infographic:** [`artifacts_agents_subtab_migration_ux_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux_infographic.png)  
**Artifact ID:** `explicit:9655bd4dcc0686030e25da8c`

---

## 1. Executive Summary & The Problem Space

Today, the SASE Terminal User Interface (TUI) splits agents across two disconnected surfaces:
1. **The Top-Level Agents Tab (`Agents`):** The operational cockpit ("flight control"). It provides real-time monitoring, live fold trees (Sessions, Clans, Tribes), unread badges, attention counts, load gauges, and rich multi-deck inspection (`Main`, `Files`, `Tools`, `Final`). However, it is restricted strictly to the active **inbox** (non-dismissed runs).
2. **The Artifacts ▸ Agent Sub-Tab (Pane `1` in `Artifacts`):** The historical catalog. It lists past agent runs across the machine, but its details panel is anemic: text-only metadata, a prompt truncated to 4,000 characters, and zero visibility into agent replies, git diffs, tool executions, or final receipts.

### The "Revival Tax" Penalty
Whenever a developer wants to inspect what an archived agent did—read its explanation, check its diff, or review its tool calls—they encounter the **Revival Tax**:
- The catalog cannot display diffs or responses.
- The developer is forced to **revive** the agent (`w` in the pane).
- Revival mutates local state, resurrects the run into the live inbox, corrupts attention signals, and clutters the active roster.
- The developer must then manually navigate back to the top-level Agents tab to read the decks.

Furthermore, housing "Agents" under the "Artifacts" tab violates core domain ergonomics: agents are active processes and execution actors, not static output artifacts like stitches, patches, beads, or plans.

---

## 2. Recommended UX Architecture & The Scoping Mental Model

We must **not** solve this by dumping all 3,500+ past agents into the live list by default. Doing so would destroy the Inbox-Zero paradigm, invalidate operational metrics (`load: 3/10`, runner slots, unread dots), and degrade keystroke latency past the 16ms p95 rule (`tui_perf`).

Instead, the solution is an **explicit, query-driven History Scope on the Agents tab**:

### 2.1 The Scope Hierarchy (`in:`)

| Scope Token | Effective Working Set | Default Behavior & Activation |
| :--- | :--- | :--- |
| `in:inbox` | Active working set: non-dismissed, non-hidden local agents + fleet runs. | **Default view.** Byte-for-byte identical to today's lightning-fast Agents cockpit. |
| `in:local` | Inbox + all locally dismissed and archived runs from the catalog. | Explicit `in:local`, leader key `,a`, or auto-widened by historical query fields. |
| `in:published` | Project-wide runs validated in the local clone of the agents git sidecar. | Explicit `in:published` or cycling `,a`. Read-only federated history. |
| `in:all` | Deduplicated union of `local` and `published` runs. | Explicit `in:all` or cycling `,a`. Comprehensive project retrospective. |

### 2.2 Progressive Disclosure & Zero-Result Widening
- **Implicit Widening (Gmail Model):** Mentioning historical attributes (e.g., `revivable:true`, `state:dismissed`, `historically_viewable:true`) automatically widens `in:inbox` to `in:local`.
- **Zero-Result Intelligent Hint:** When an inbox query returns 0 matches, a fast background index check tests the local catalog. If matches exist, the info row suggests:
  ```text
  0 in inbox · 14 in local history — press ,a or <Enter> to widen scope
  ```
- **Scope Cycling Shortcut (`,a`):** Leader `,a` (currently unbound in `default_config.yml`) cycles through scopes:
  $$\text{in:inbox} \xrightarrow{,a} \text{in:local} \xrightarrow{,a} \text{in:all} \xrightarrow{,a} \text{in:inbox}$$

---

## 3. Visual Wireframes & Interaction Design

### 3.1 Artifacts Tab Simplification
The `Agents` pane is removed from Artifacts. `Stitches` (◉) becomes digit `1`, aligning keyboard navigation directly with the default pane:
```text
Old: [1: Agents] [2: Stitches] [3: Patches] [4: Beads] [5: Files] [6: Plans]
New: [1: Stitches] [2: Patches] [3: Beads] [4: Files] [5: Plans]
```
Legacy references and links (`artifacts:agents`, `sase artifact pane show agents`) redirect gracefully to the Agents tab with scope `in:local`.

### 3.2 Full-Screen Terminal Wireframe: Agents Tab in History Mode (`in:local`)
When History mode is activated, the Agents tab transitions into a retrospective inspection suite:
- The top header replaces the live load gauge with the prominent **Scope Chip** (`⌸ SCOPE: LOCAL HISTORY`).
- The left column replaces the live fold tree with the virtualized **History Stream** (lightweight rows grouped by Date/Session/Project with provenance and status badges).
- The right column provides **THE REAL LIVE DECKS (Read Without Revive)**!

```text
┌─ SASE TUI v0.24 · Project: sase (apollo) ──────────────────────────────────────────────────────────────────────────────────┐
│ Artifacts   ● AGENTS   Services                                                            ARCHIVE SEARCH · Apollo · 14:25 │
├────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ ⌸ SCOPE: LOCAL HISTORY │ filter: in:local project:sase [14/1,456 matches] (/) │ Metrics: 14 matching · 10 revivable · 4 thin│
├──────────────────────────────────────────────┬─────────────────────────────────────────────────────────────────────────────┤
│ HISTORY STREAM (Grouped by Date)             │ DECK AREA: [1: MAIN]  2: FILES  3: TOOLS  4: FINAL               (p to pick)│
├──────────────────────────────────────────────┼─────────────────────────────────────────────────────────────────────────────┤
│ ▼ TODAY (Oct 08, 2026)                       │ ╭─ AGENT: sase-10j.worker2 · [ARCHIVED] ────────────── [✓ READ WITHOUT REV]│ │
│   sase-10j.worker2  [DONE] [here]    4m 12s ◄┼─┤ Status: DONE   Duration: 4m 12s   Finished: 13:09:15   Cost: $0.042       │ │
│   sase-9f.refactor  [FAIL] [here]    1m 45s  │ │ Model: claude-3-7-sonnet   Session: sess-8890   Bead: sase-10j (Closed)  │ │
│                                              │ ╰─────────────────────────────────────────────────────────────────────────╯ │
│ ▼ YESTERDAY (Oct 07, 2026)                   │ ╭─ ORIGINAL PROMPT (Full Transcript Preserved) ───────────────────────────╮ │
│   research.44.cld   [DONE] [here+pub]12m04s  │ │ Fix the catalog schema version coupling in _sources.py where            │ │
│   chop.apollo.88    [DONE] [pub·ath] 2m 10s  │ │ AGENT_ARTIFACT_INDEX_SCHEMA_VERSION was hardcoded to 34 instead of      │ │
│   sase-8a.invest    [WAS ACTIVE]     Stale   │ │ reading the Rust binding version (35). Verify with just check.          │ │
│                                              │ ╰─────────────────────────────────────────────────────────────────────────╯ │
│ ▼ OCTOBER 05, 2026                           │ ╭─ AGENT REPLY / FINAL OUTPUT ────────────────────────────────────────────╮ │
│   chop.apollo.81    [DONE] [here]    5m 20s  │ │ Successfully patched _sources.py to read dynamic schema version from    │ │
│   sase-7x.ui-audit  [DONE] [here]    3m 44s  │ │ sase_core_rs. Ran pytest tests/test_agent_catalog.py (all 14 passed).   │ │
│   sase-7w.docs-sync [DONE] [here]    1m 12s  │ │ Final declaration submitted with commit sha 75e27f9.                     │ │
│                                              │ ╰─────────────────────────────────────────────────────────────────────────╯ │
├──────────────────────────────────────────────┴─────────────────────────────────────────────────────────────────────────────┤
│ Enter Actions (Revive/Fork/View) · r Revive · f Fork · e Diff · %@ Copy Ref · ,a Cycle Scope · [ / ] Deck · ^ Undo Filter  │
└────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

### 3.3 The Four Decks in History Mode (Read Without Revive)
- **`MAIN` Deck:** Full original prompt (not truncated!), rendered agent response, session lineage, cost, token metrics, and associated planning beads.
- **`FILES` Deck:** Full syntax-highlighted git diff of what the agent modified, with touch list and patch status.
- **`TOOLS` Deck:** Execution history of all tool calls, arguments, execution duration, and stdout/stderr output.
- **`FINAL` Deck:** Host finalizer declaration manifest, commit SHA, and verification command receipts (`just check` pass/fail).
- **Graceful Retention Degradation:** If an agent's workspace files were pruned by retention policies, a clean card informs the user that prompt, chat transcript, commit SHA, and receipts remain fully preserved.

### 3.4 Keybinding Harmonization & The Action Chooser
To resolve the key collision between the pane's `w` revive and the Agents tab's `w` reword:
1. **The History Action Chooser (`Enter`):** Pressing `Enter` on any historical row opens a clean modal:
   - `[1] Revive Agent (r)` (default item for revivable agents)
   - `[2] Read Decks (v)`
   - `[3] Copy Reference (@)`
   - `[4] Fork as New Agent (f)`
   - `[5] View Commit in Stitches (s)`
   - `[6] Open Diff in External Editor (e)`
2. **Dedicated Hotkey (`r`):** In History mode, `r` triggers immediate revival for highlighted revivable runs.
3. **Custom Revival Search (`!R`):** Retargeted from the Artifacts pane to commit `in:local state:dismissed revivable:true` directly on the Agents tab.

---

## 4. Performance & Data Flow Architecture

The design guarantees compliance with SASE's `tui_perf` rules (Rule 1 & 2 event loop hermeticity, Rule 9 startup speed, Rule 11 worker cancellation):

```text
User Query / Scope Token (e.g. in:local)
                │
                ▼
      Query Evaluator (sase-core)
                │
     ┌──────────┴──────────┐
     ▼                     ▼
Local Catalog (SQLite)  Sidecar Manifest (HEAD cache)
     │                     │
     └──────────┬──────────┘
                ▼
 Tier 1: Lightweight Row Tuples (<5ms)
 (Name, Status, Time, Provenance, Revivable)
                │
                ▼
 History Stream Virtual List
                │
                ▼  (Highlighted Row - Debounced 25ms)
 Tier 2: Lazy Deck Hydration (<15ms)
 (Reads dismissed bundle: agent_meta, prompt, chat, diffs)
                │
                ▼
 Render Rich Decks (Read Without Revive)
```

- **Honest Provenance:** Non-terminal published runs in the sidecar started $\ge 2$ days ago render with `WAS ACTIVE · as of <time>` (muted gold), never `RUNNING`.
- **Deduplication:** Local and published runs are deduplicated by `source_run_id`.

---

## 5. Summary of Recommended Implementation Roadmap

| Phase | Milestone Name | Scope & Deliverables |
| :---: | :--- | :--- |
| **P0** | **Catalog Schema Coupling Fix** | Dynamically read `AGENT_ARTIFACT_INDEX_SCHEMA_VERSION` from `sase_core_rs` instead of a static Python constant, un-breaking catalog metadata enrichment. |
| **P1** | **Dialect Unification** | Add `in:` scope token, implicit widening, and catalog lifecycle fields (`state`, `dismissed`, `revivable`, `linked`, `relation`) to `agents-live` schema. |
| **P2** | **History Mode & Decks** | Implement History Stream option list and lazy deck hydration for dismissed bundles. Deliver **Read Without Revive**. |
| **P3** | **Actions & Navigation Parity** | Implement History Action Chooser on `Enter`, hotkey `r`, leader `,a`, and retarget `!R` and `agent:` links. |
| **P4** | **Artifacts Pane Retirement** | Deprecate `ArtifactsAgentsPane` behind `sunset_artifacts_agents_pane`. Renumber Artifacts digits (Stitches becomes `1`). |
| **P5** | **Published Sidecar History** | Implement Rust sidecar projection, `source_run_id` deduplication, and `WAS ACTIVE` presentation for `in:published`. |

---

## Deliverables & Registration Record

1. **Full Research Report:** [`sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md)
2. **Companion Infographic:** [`sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux_infographic.png)
3. **Durable SASE Artifact Registration:**  
   `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md" -l "research:202610/artifacts_agents_subtab_migration_ux/artifacts_agents_subtab_migration_ux__gem.md"`  
   **Result:** `file:explicit:9655bd4dcc0686030e25da8c` (Status: live, exact resolution).
4. **Final Declaration:** Host finalizer commit declaration submitted and accepted for `sdd:research` (`repo-2fa36a51a90c`).
