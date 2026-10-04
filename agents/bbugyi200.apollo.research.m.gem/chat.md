# Chat History - ace-run (research.m.gem)

- **TIMESTAMP:** 2026-09-28 18:42:36 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.m.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_183346.md`

## Prompt

%id(gem, clan=research.m)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.m.cdx`, `research.m.cld`, `research.m.grk`, `research.m.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think I just want
to get rid of the "Agent" sub-tab of the "Artifacts" tab in favor of integrating that
sub-tab's functionality into the "Agents" tab, by making any agent ever run locally (on
the current machine) or on the current project (i.e. a sase agent that was published to
the agents sidecar repo) accessible. I'm not sure what the UX would like like this
though (maybe use the sase agent query language, if there is one?).

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

# Research & Architectural Critique: Unifying Agent Artifacts into the Agents Tab and Sidecar Catalog

**Author:** Researcher `gem` (5-Researcher Swarm)  
**Report Artifact:** `research:202609/agents_tab_unified_history_and_sidecar_catalog__gem.md`  
**Ref:** `file:explicit:ff65f27df467aa4781a0fe00`  
**Report File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_26/sase/repos/research/202609/agents_tab_unified_history_and_sidecar_catalog__gem.md`

---

## 1. Executive Summary & Core Verdict

### Is getting rid of the "Agent" sub-tab in Artifacts a good idea?
**Yes, unequivocally.**
- **Eliminates cognitive dissonance:** Maintaining two separate "Agents" surfaces—the top-level **Agents** tab (`#agents-view`) for live runs and the **Artifacts -> Agent** sub-tab (`#artifacts-agents-pane`) for historical runs—confuses users who wonder where a completed run lives.
- **Restores ontological clarity to Artifacts:** The Artifacts tab represents deliverables and work units: Stitches (commits), Patches (PRs), Beads (tasks/issues), Plans, and Files. **Agents are autonomous actors, not artifacts.**

### Is bringing all historical and sidecar-published agents into the Agents tab a good idea?
**Yes, but only with a two-tier scope architecture.**
- **The Scale Trap:** A naive merge dumping 3,000–10,000+ historical runs into the live `AgentList` widget will starve the Textual asyncio event loop, trigger excessive memory consumption, and drown the engineer's active working set in stale noise.
- **The Sidecar Latency Trap:** The project's `agents` sidecar repository is an owner-sharded Git repository. Parsing it synchronously during TUI startup or live refreshes would introduce multi-second freezes.
- **Verdict & Recommendation:** Implement an **Active Working Set (Inbox Scope)** as the default view, and provide instant access to the **Full Historical & Sidecar Catalog (Corpus Scope)** through a dedicated `[Catalog]` chip in `AgentTabStrip` and unified boolean query bridging.

---

## 2. Key Findings: SASE's Current Architecture

### 2.1 The Two Disconnected Worlds in Code
1. **The Live Agents Tab (`src/sase/ace/tui/`)**:
   - **Engine:** `load_tiered_agents` (Tier 1 head: ~200-500 recent runs, ProjectSpec `RUNNING` claims, active PID polling every 1–2s).
   - **Model:** Heavyweight `Agent` dataclass (~50 fields: runner slots, tmux handles, gates, notification overrides).
   - **UI:** `AgentsFilterBar` running the `agents-live` profile (`src/sase/ace/query_profile/profiles/_agents_live.py`), `AgentTabStrip`, `AgentList`, and `AgentDetail` (Decks & Cards).
   - **Blind spot:** Blind to older completed/dismissed runs and blind to remote agents in the sidecar.
2. **The Artifacts -> Agent Sub-Tab (`src/sase/ace/tui/widgets/artifacts/`)**:
   - **Engine:** `build_agent_catalog_snapshot()` spined on `agent_name_registry.json` (`~/.sase/`), left-joined with lean projection columns from SQLite `agent_artifacts.db` and dismissed bundle summaries.
   - **Model:** Lightweight, immutable `AgentCatalogRow` tuples.
   - **UI:** `AgentFilterBar` running the boolean `agents` profile (`src/sase/ace/query_profile/profiles/_agents.py`), `AgentsOptionList`, `RelationPanel` (links to stitches, patches, beads, plans), and lazy prompt/chat loaders.
   - **Blind spot:** Disconnected from live operations; also blind to sidecar runs from other machines.

### 2.2 SASE's Agent Query Language
SASE already has a Rust-backed boolean query engine evaluated via `compile_query_with_profile` and `evaluate_many`. However, two profiles currently exist:
- **`agents` (Catalog profile):** Supports `state:active|done|dismissed`, `relation:read|wrote`, `linked:bool`, `revivable:bool`, `durably_revivable:bool`, date bounds (`since:7d`, `until:today`), runtime bounds (`min:5m`, `max:1h`), and full boolean logic (`AND`, `OR`, `NOT`, parens).
- **`agents-live` (Live profile):** Supports 27 live statuses (`QUESTION`, `PLAN APPROVED`, `FEEDBACK`), `needs:input`, `source:axe|manual`, `cl:<patch>`, `machine:<host>`, `tab:<name>`, `pinned:bool`, `unread:bool`.
- **Action:** Merge both into a single **`agents-unified`** profile.

---

## 3. Critique of Requirements & Recommended Adjustments

| Original Requirement | Critique & Risk | Recommended Adjustment |
| :--- | :--- | :--- |
| **"Get rid of the Agent sub-tab in Artifacts"** | High value, zero negative side effects on Artifacts tab. | **Proceed immediately.** Shift `DEFAULT_ARTIFACTS_SUBTAB` to `stitches`. Preserve backward compatibility by redirecting legacy `artifacts:agents` requests to `agents:catalog`. |
| **"Make any agent ever run locally accessible in Agents tab"** | Naively loading 10,000 agents into the live `AgentList` causes memory bloat and UI lag during 1s delta polling. | **Two-Tier Scope Architecture:** Default to the **Active Working Set (Inbox)**; access the full historical catalog via a **`[◈ Catalog]`** tab in `AgentTabStrip` or filter expansion. |
| **"Make any agent published to the agents sidecar repo accessible"** | Walking Git trees in `~/.sase/projects/.../repos/agents` during UI startup causes multi-second freezes. | **Asynchronous Sidecar Harvester:** Ingest sidecar metadata into a local SQLite table (`sidecar_agents`) during `sase agent sync` and background idle intervals. |
| **"Retain Artifacts -> Agent functionality"** | Removing the pane risks discarding the beloved `RelationPanel` (which links agents to commits, PRs, and beads). | **Deck & Card Integration:** Port the `RelationPanel` into the Agents tab's detail view as an **`ArtifactRelationsCard`** in `AgentDetailDeckMixin`. |

---

## 4. Recommended UX Design

### 4.1 Visual Wireframe (Top-Level Agents Tab)
```text
┌─ ACE: sase ──────────────────────────────────────────────────────────────────────────────────┐
│ [1: Agents]  [2: Artifacts]  [3: Services]                           Load: 12%  Slots: 3/8   │
├──────────────────────────────────────────────────────────────────────────────────────────────┤
│ Agents: 2 running, 1 waiting input                                    Filter: (none) [/]     │
│ [• Main (3)] [◈ Catalog (3,842)] [⌨ apollo (1)] [⌨ athena (0)]                                │
├──────────────────────────────────────────────────────┬───────────────────────────────────────┤
│ Catalog (Local + Sidecar)                            │ Agent: sase.fix-tui-flicker.3         │
│ Filter: [project:sase provider:codex status:DONE   ] │ Status: DONE (2026-09-24 14:22 UTC)  │
├──────────────────────────────────────────────────────┼───────────────────────────────────────┤
│ ● sase.fix-tui-flicker.3   codex  2026-09-24 [local] │ ╭─ Metadata Deck ───────────────────╮ │
│ ● sase.auth-token-refresh  claude 2026-09-23 [sidecar]│ │ Project: sase      Role: code       │ │
│ ▲ sase.ci-matrix-repair    codex  2026-09-22 [apollo]│ │ Provider: codex    Model: gpt-5.4   │ │
│ ■ sase.bead-graph-cache    grok   2026-09-20 [sidecar]│ │ Duration: 4m 12s   Attempts: 1      │ │
│ ● sase.rust-core-sync.12   claude 2026-09-18 [local] │ ╰─────────────────────────────────────╯ │
│                                                      │ ╭─ Artifact Relations Deck ─────────╮ │
│                                                      │ │ ◉ Stitch: 8f3a1b2 ("Fix flicker") │ │
│                                                      │ │ ⎇ Patch:  PR #482 (Merged)        │ │
│                                                      │ │ ◈ Bead:   sase-99a (Closed)       │ │
│                                                      │ │ ▤ File:   src/sase/ace/tui/app.py │ │
│                                                      │ ╰─────────────────────────────────────╯ │
│                                                      │ ╭─ Actions ─────────────────────────╮ │
│                                                      │ │ [R] Revive  [C] Copy Ref  [P] Prompt│ │
│                                                      │ ╰─────────────────────────────────────╯ │
├──────────────────────────────────────────────────────┴───────────────────────────────────────┤
│ [j/k] Navigate  [/] Filter  [Tab] Switch Tab  [r] Revive  [p] View Prompt  [c] View Chat     │
└──────────────────────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Key Interactions
1. **Default State (`[• Main]` tab):** Displays only active, waiting, and recent terminal agents. Real-time delta polling tracks runner slots, PIDs, and HITL notification gates.
2. **Catalog State (`[◈ Catalog]` tab):** Displays all runs (local registry + sidecar records) sorted newest-first with `[local]`, `[sidecar]`, or machine badges (`[apollo]`). Delta polling is paused.
3. **Filter Bar Bridging:** Pressing `/` in the `Main` tab filters live agents. If no live agents match, the filter bar displays an inline shortcut:  
   `"0 active matches · 14 catalog matches (Press Tab/Enter to view in Catalog)"`.

---

## 5. Technical Implementation Roadmap

1. **Phase 1: Asynchronous Sidecar Harvester (`sase.agents.sidecar`)**
   - Add a `sidecar_agents` table to `~/.sase/agent_artifacts.db` indexing `(global_name, name, project, user, machine, started_at, status, model, provider, prompt_path, chat_path)`.
   - Implement `harvest_agents_sidecar(project_key)` reading sidecar manifests and caching metadata. Hook into `sase agent sync` and background TUI idle tasks.
2. **Phase 2: Unified Catalog Spining (`sase.agents.catalog`)**
   - Update `build_agent_catalog_snapshot()` to union local records from `agent_name_registry.json` with remote records from `sidecar_agents`.
   - Merge duplicate identities (local run that synced to sidecar) into a single row marked `Provenance.SYNCED`.
3. **Phase 3: Query Profile Unification (`sase.ace.query_profile`)**
   - Consolidate `_agents.py` and `_agents_live.py` into `agents-unified`, supporting `origin:local|sidecar`, `scope:live|catalog`, relations, and live operational states.
4. **Phase 4: Agents Tab Integration (`src/sase/ace/tui/`)**
   - Extend `AgentTabKey` with `AgentTabKey.catalog()`.
   - Add the `[Catalog]` chip to `AgentTabStrip`.
   - Introduce `ArtifactRelationsCard` in `_agent_detail_decks.py` to display linked stitches, patches, and beads.
5. **Phase 5: Clean Retirement of Artifacts -> Agent Sub-Tab**
   - Remove `"agents"` from `FIXED_ARTIFACTS_SUBTAB_ORDER` in `_artifact_tab_model.py`.
   - Remove `#artifacts-agents-pane` mounting from `ArtifactsView`.
   - Add a redirect for legacy configuration keys.

---

## 6. Registration & Turn Status
- **Research File:** Created at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_26/sase/repos/research/202609/agents_tab_unified_history_and_sidecar_catalog__gem.md`.
- **Durable Artifact Registration:** Succeeded with reference `file:explicit:ff65f27df467aa4781a0fe00` under label `research:202609/agents_tab_unified_history_and_sidecar_catalog__gem.md`.
- **Finalizer Declaration:** Submitted and accepted via `sase final submit` for repository `sdd:research`.
