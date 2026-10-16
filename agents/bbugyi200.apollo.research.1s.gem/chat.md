# Chat History - ace-run (research.1s.gem)

- **TIMESTAMP:** 2026-10-16 17:55:40 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1s.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_173700.md`

## Prompt

%id(gem, clan=research.1s)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.1s.cdx`, `research.1s.cld`, `research.1s.grk`, `research.1s.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
recently did some research related to the creation of a new `sase project stats` command
(see the project_stats_cli_design.md file in the research sidecar repo for context).

- This research was performed before I had fully fleshed out the requirements.
- This command should be named `sase stats project` instead of `sase project stats` (the
  `sase stats` command will be new).
- My long-term goal (the entirety of which is out-of-scope for your research) is to make
  it so the data from every sub-tab on the "Statistics" tab of the "SASE Admin Center"
  panel is accessible via a `sase stats` sub-command that fetches the data using the
  same code paths as the TUI.
- As a part of this initial change, we will set ourselves up for this work by migrating
  the "Projects" sub-tab to use the same data source as the new `sase stats project`
  command.
- Finally, I forgot to mention to the previous research agents that this command should
  also track how many commits were made by each model/provider and how many plans were
  committed by each model/provider.
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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: `sase stats project` Architecture, Critique, and Design

**Author:** researcher gem (`__gem`)  
**Date:** 2026-10-16  
**Artifact ID:** `explicit:0813ba8e982fdfa41148ff19`  
**Report File:** [`sase_stats_project_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/sase_stats_project_design__gem.md)  
**Registered Reference:** `file:explicit:0813ba8e982fdfa41148ff19` (`research:202610/sase_stats_project_design__gem.md`)

---

## 1. Executive Summary & Assessment

Your plan to introduce the new `sase stats` command tree with `sase stats project` as its leading implementation, while simultaneously migrating the TUI Admin Center "Projects" statistics sub-tab to use the exact same data source, is an **architecturally sound and high-value strategy**.

### Why This Is a Great Idea
1. **1:1 Cognitive Alignment Between TUI and CLI:** The SASE Admin Center Statistics modal contains eight sub-tabs (`overview`, `runners`, `projects`, `providers`, `activity`, `macros`, `plans_questions`, `perf`). Today, these rich analytics are locked inside interactive TUI modals. Establishing the top-level `sase stats` command tree creates direct parity: `sase stats project`, `sase stats runner`, `sase stats provider`, etc.
2. **Eliminates Definitional Drift:** Re-deriving metrics through ad-hoc scripts or one-off git commands produces conflicting figures. Consolidating on a single, shared Rust/Python data pipeline guarantees that the terminal CLI, automated agent queries, and interactive TUI panels report identical numbers.
3. **Surfaces Unprecedented Intelligence:** Tracking commits and committed architectural plans by model and provider transforms `sase stats project` from a simple code counter into a strategic capability report on multi-model AI swarms.

---

## 2. Critique of the Plan & Required Adjustments

While the overall vision is compelling, our research uncovered two critical technical tensions that require deliberate design adjustments:

### Tension 1: The Codebase vs. Production Telemetry Gap
- **Previous research** (`project_stats_cli_design.md`) treated project stats purely as a static git repository measurement (lines of code, git commits, active days, languages).
- **The current TUI "Projects" sub-tab** treats project stats purely as dynamic agent run telemetry (runs, wall-clock time, success rate, patches).
- **Resolution (Two-Facet Domain):** Neither view should replace the other. We recommend unifying them into a **two-facet domain model**:
  - **Facet A (Codebase Architecture):** Git commits, SLOC via tokei, test share %, doc lines, active days, top languages.
  - **Facet B (Agent Production & Economics):** Agent runs, success rate, wall time, patches, commits by model/provider, and committed plans by model/provider.
  Both the CLI and TUI consume this unified model.

### Tension 2: TUI Event-Loop Latency vs. Cold Git Walks
- Cold git repository walks (tree traversals, blob streams, and tokei SLOC analysis) take **2.2 to 5.0 seconds** on large repos like `sase`.
- The TUI requires sub-100ms response times to avoid UI stalls (violating `tui_perf.md`).
- **Resolution (Decoupled Shared Provider):** The shared service in `sase.stats` must decouple fast SQLite agent queries (<15ms) from git repo scanning. In the TUI, repo codebase metrics are served from an in-memory/TTL cache with lazy background refresh, while the CLI runs both synchronously.

### Ground Truth: Commits and Committed Plans by Model/Provider
Querying our live environment (`~/.sase/agent_artifact_index.sqlite` and git history) revealed:
- **Committed Plans (1,662 total in active index):** SASE already records `plan_committed: true` in `agent_meta.json` upon gate approval. The live index breaks down as:
  - **Muse (`muse-spark-1.3-contributor`):** 666 plans (40.1%)
  - **Claude (`opus`):** 306 plans (18.4%)
  - **Codex (`gpt-6-luna`):** 154 plans (9.3%)
  - **Grok (`grok-4.6`):** 150 plans (9.0%)
  - **Grok (`grok-4.7`):** 88 plans (5.3%)
  - *Remaining 8 models:* 298 plans (17.9%)
- **Attributed Commits (1,757 in active index):** Muse leads with 783, Grok with 319, Codex with 341, Claude with 301, and Gemini/AGY with 13.
- **Attribution Horizon:** SASE git history has **8,598 agent-signed commits** dating back to May 2026, while the local SQLite index covers runs from September 1, 2026 forward (~45-day retention). The command must report attribution coverage clearly so users understand the indexed horizon vs all-time repository commits.

---

## 3. Recommended CLI & TUI Design

### 3.1 CLI Surface
```text
usage: sase stats project [-h] [-d] [-D] [-f {auto,csv,json,markdown,table}] [-F] [-j]
                          [-r NAME] [-t RANGE] [PROJECT ...]

Report unified repository and agent production statistics for SASE projects.
```
- **Positional:** `PROJECT` (defaults to all enabled projects, matching `sase project list`).
- **Options:**
  - `-t, --range {today,24h,7d,30d,90d,all}`: Time window for agent activity, commits by model, and plans (default: `30d` or `all`).
  - `-d, --details`: Extends output with per-repo tables, model breakdowns, and file roles.
  - `-f, --format {auto,csv,json,markdown,table}`: Output format (`auto` = Rich table on TTY, Markdown when piped).
  - `-F, --fetch`: Fetch remote refs before measuring git codebase stats.
  - `-j, --json`: Shorthand for `--format json`.
  - `-r, --repo NAME`: Filter to specific repositories.

### 3.2 Terminal Visual Layout (`sase stats project sase`)

```text
╭─ sase · +sase ────────────────────────────────── Range: Last 30 Days (2026-09-16 → 2026-10-16) ─╮
│                                                                                                │
│   CODEBASE TRUTH (Snapshot)                                                                    │
│   Active       Feb 14, 2026 · 244 days old · commits on 239 distinct days                      │
│   Commits      18,327 total (6 code repos) · 9,839 agent-signed (53.7%)                        │
│   Lines        3,126,927 SLOC in 13,964 files · 46.2% tests · 81,941 doc lines                 │
│   Languages    █████████████████████████████████████████████▓▓▓▓▓▓▓▓░  Python 82% · Rust 17%   │
│                                                                                                │
│   AGENT PRODUCTION (Last 30 Days)                                                              │
│   Runs         1,854 runs · 91.2% completed · 142.6 hours wall clock · 28 distinct patches     │
│   Production   1,850 commits (98.9% agent-signed) · 246 plans proposed · 218 plans committed   │
│                                                                                                │
│   MODEL & PROVIDER CONTRIBUTIONS (Commits & Plans Committed)                                   │
│   PROVIDER   MODEL                       COMMITS   SHARE   COMMITTED PLANS   PLAN SHARE        │
│   muse       muse-spark-1.3-contributor      783   44.6%               112        51.4%        │
│   grok       grok-4.6                        319   18.2%                34        15.6%        │
│   codex      gpt-6-luna                      249   14.2%                31        14.2%        │
│   claude     sonnet                          169    9.6%                18         8.3%        │
│   claude     opus                            132    7.5%                14         6.4%        │
│   other      (4 models)                       89    5.1%                 9         4.1%        │
│                                                                                                │
╰────────────────────────────────────────────────────────────────────────────────────────────────╯

  CODE REPOS (Totaled)              COMMITS   AGENT   30 DAYS   FIRST COMMIT   CODE LINES   TESTS   DOC LINES
  sase                     primary   16,181     53%     1,850     2026-02-14    2,521,676     51%      73,717
  sase-core                linked     1,563     62%       396     2026-04-28      536,490    22%¹       3,503
  sase-telegram            linked       307     36%        40     2026-02-28       33,698     53%       1,255
  sase-listen              linked        34     82%        34     2026-10-01       22,070     34%       1,633
  sase-github              linked       174     41%        26     2026-02-23       10,205     59%         651
  sase-research-artifacts  linked        68     93%        31     2026-08-11        2,788     91%       1,182
  ────────────────────────────────────────────────────────────────────────────────────────────────────────
  Total (6 of 7 repos)               18,327     54%     2,377     2026-02-14    3,126,927     46%      81,941

  RECORDS (Sidecars, Never Totaled) COMMITS    FILES   FIRST COMMIT   LAST COMMIT
  beads                              23,378    8,655     2026-07-28   3 min ago
  plans                               9,458    7,750     2026-07-11   1 hour ago
  agents                              8,335  129,152     2026-07-23   5 min ago
  research                            2,067    5,272     2026-07-11   12 min ago
```

### 3.3 Migrated TUI "Projects" Sub-tab
The Admin Center "Projects" sub-tab in `src/sase/ace/tui/modals/statistics_pane_projects.py` is upgraded to render:
1. **Top Metric Strip:** Total projects, codebase SLOC, test share %, active days.
2. **Projects Table:** Projects, Repos (e.g. `6/7`), Total Commits, Agent %, SLOC, Runs, Success %, Committed Plans.
3. **Model Contribution Bar:** Visual horizontal proportion bars for commits and committed plans by provider.

---

## 4. Architectural Roadmap & Delivery Steps

1. **Rust Core Backend (`sase-core`):**
   - Extend `AgentCommitStatsWire` and `AgentPlanStatsWire` in `crates/sase_core/src/agent_stats/run/wire.rs` with `commits_by_provider` and `plans_committed_by_provider`.
   - Update `fold_commits` and `fold_plans` in `crates/sase_core/src/agent_stats/run/folds.rs` to group by `(provider, model)`.
   - Implement `project_stats::collect` in `crates/sase_core/src/project_stats/` for git log and tokei SLOC walks.
2. **Python Facade (`sase.stats`):**
   - Update `src/sase/stats/_view_models.py` (`ProjectsView`) and `src/sase/stats/_view_builders.py`.
   - Implement `src/sase/stats/project_service.py` with an in-memory TTL cache for git scans to protect TUI frame rates.
3. **CLI Command Tree (`sase stats`):**
   - Register `"stats"` in `src/sase/main/parser_registry.py` and implement `src/sase/main/parser_stats.py`.
   - Implement `src/sase/main/stats_handler_project.py` with full support for `table`, `markdown`, `json`, and `csv`.
4. **TUI Migration:**
   - Update `StatisticsProjectsRenderingMixin` in `src/sase/ace/tui/modals/statistics_pane_projects.py` to consume the new `ProjectsView`.
5. **Verification:**
   - Execute verification suite via `just check`.

---

The complete, unabridged research document has been saved to:  
[`sase_stats_project_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/sase_stats_project_design__gem.md)  
and registered as durable artifact: `explicit:0813ba8e982fdfa41148ff19`.

The finalizer declaration for the `commit` payload (`repo-8caa19a02d02` in `sdd:research` covering `202610/sase_stats_project_design__gem.md`) was successfully submitted and accepted by the host.
