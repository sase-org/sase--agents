# Chat History - ace-run (research.1q.gem)

- **TIMESTAMP:** 2026-10-16 16:13:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1q.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_155151.md`

## Prompt

%id(gem, clan=research.1q)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.1q.cdx`, `research.1q.cld`, `research.1q.grk`, `research.1q.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
would like to add a new `sase project stats <project_name>` command, where
`<project_name>` is an optional sase project name, that produces useful stats about a
specific (or all if `<project_name>` is not specified) sase project.

- These numbers should include, but not be limited to (think hard about what stats would
  be genuinely useful to users): commit counts, line counts (for code files and docs),
  file counts (for code files and docs), length of time the project has been active.
- We should show numbers for all repos linked to the targeted project(s), but the stats
  should be separated by repo.
- We should support various formats that are useful to humans, agents, and scripts.
  Think hard about which formats to support and what the `sase project stats` command's
  output should look like for each format.
- This will be useful, for example, when gathering the numbers I plan on listing in
  sase's launch post (see the sase_launch_post_outline.md file in the research sidecar
  repo for context).
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

# Research & Technical Design: `sase project stats` Command

I have completed the research, architectural design, and critique for the proposed `sase project stats [<project_name>]` command. The full report has been written and permanently registered as an artifact.

- **Report File:** [`sase_project_stats_command_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_project_stats_command_design__gem.md)
- **Artifact Reference:** `file:explicit:8f6ad097e6ba24d20e840d24`
- **Artifact Label:** `research:202610/sase_project_stats_command_design__gem.md`

Below is an executive synthesis of the findings, critique, metric recommendations, and implementation design.

---

## 1. Executive Critique: Is This a Good Idea?

### The Verdict: Strongly Recommended (With Four Vital Adjustments)
Standard developer tools (`git`, `cloc`, `tokei`) are single-repository centric. SASE projects, however, are multi-repo ecosystems spanning primary codebases, Rust engine backends (`sase-core`), sidecars (`beads`, `plans`, `research`, `agents`), and plugin integrations (`sase-github`, `sase-telegram`, `sase-nvim`, `sase-listen`). 

A native `sase project stats` command bridges the gap between raw git history and SASE's agentic engineering model, providing a single source of truth for repository velocity, codebase composition, and living task state.

### Recommended Adjustments to the Requirements

1. **Default Target Resolution (Avoid Unintentional Multi-Project Scans):**
   - *Original Requirement:* If `<project_name>` is omitted, produce stats for all projects.
   - *Recommended Adjustment:* Default to the **current project** (inferred from the current workspace directory), exactly matching `sase repo list` and `sase bead list`. Provide `-a` / `--all` to explicitly scan all registered projects.
   - *Rationale:* Defaulting to all projects when running inside an active workspace checkout violates SASE's workspace-centric conventions and causes unexpected multi-repo disk I/O across unrelated projects.
2. **Repository Boundary Scoping:**
   - *Original Requirement:* Show numbers for all repos linked to the project.
   - *Recommended Adjustment:* Include `primary`, `linked`, and `sidecar` repos by default, but **explicitly exclude** opened `external` checkouts unless `--include-external` is passed.
   - *Rationale:* SASE agents open third-party repositories via `/sase_repo` (e.g. `gh:remsky/Kokoro-FastAPI`, `gh:arcivanov/pypi-cleanup`). Including external checkouts would distort the project's true code metrics with foreign code.
3. **Granular Classification (Source vs. Test vs. Docs):**
   - *Original Requirement:* Line counts and file counts for code files and docs.
   - *Recommended Adjustment:* Differentiate **Implementation Source Code** from **Test Suites** (`tests/`, `*_test.py`, `tests.rs`).
   - *Rationale:* In SASE, tests account for **1.29 million lines** across 6,310 files, while implementation source accounts for **1.18 million lines** across 5,951 files. Lumping tests into "code" obscures the test-to-implementation symmetry (1.09:1 ratio).
4. **Graceful Handling of Uncloned Checkouts:**
   - Ephemeral workspaces clone secondary repos on demand (e.g., `sase-nvim` is not auto-cloned in workspace 17). The command must inspect clone status via `RepoInventory` and report uncloned checkouts cleanly as `[not cloned]` rather than raising unhandled errors.

---

## 2. Metric Catalog: What Genuinely Matters?

Beyond simple line counts, `sase project stats` should surface the metrics that define structured agentic engineering:

1. **The "Agentic Dividend" (Autonomy Metrics):**
   - **Total Commits vs. Agent Commits:** By parsing SASE commit footers (`SASE_AGENT=[<identity>]`), track exactly how many commits were authored autonomously by agents vs. humans.
   - **Agent Contribution Ratio:** Expressed as an overall percentage across the ecosystem and per repository.
2. **Velocity & Activity Lifespan:**
   - **Calendar Lifespan:** Elapsed time from root commit (`git rev-list --max-parents=0 HEAD`) to `HEAD` (e.g., `8.0 months`).
   - **Active Commit Days:** Count of distinct calendar days on which commits occurred (`git log --format=%as | sort -u | wc -l`). For `sase`, commits were made on **239 out of 244 calendar days** (97.9% active density).
   - **Commit Cadence:** Average commits per active day (~68 commits/day).
3. **Codebase Density & Test Rigor:**
   - Source LOC (Python, Rust, Shell, etc.).
   - Test LOC and **Test-to-Source Ratio** (1.09:1).
   - Documentation & Memory LOC (`docs/`, `sase/memory/`, `plans/`, `research/`).
4. **Living Work State (Beads & Sessions):**
   - Closed vs. Ready vs. In-Progress Beads.
   - Bead distribution across Plans, Phases, Tasks, and Flags.
   - Total archived agent sessions (`agents` sidecar).

---

## 3. Live Benchmark Data: Project `sase` (Measured 2026-10-16)

The research gathered live, verified metrics directly from the `sase` project repositories in workspace `sase_17`, providing the exact numbers needed for `sase_launch_post_outline.md`:

| Repository | Kind | Total Commits | Agent Commits | Agent % | Source LOC | Test LOC | Docs LOC | Active Days |
|---|---|---|---|---|---|---|---|---|
| `sase` | Primary | **16,181** | 6,774 | 41.9% | 1,183,464 | 1,288,706 | 97,639 | 239 |
| `sase-core` | Linked (Rust) | **1,563** | 886 | 56.7% | 529,632 | — | 5,702 | 149 |
| `plans` | Sidecar | **9,456** | 7,135 | 75.5% | — | — | 184,210 | 96 |
| `research` | Sidecar | **2,064** | 1,931 | 93.6% | — | — | 98,400 | 84 |
| `agents` | Sidecar | **8,334** | 13 | 0.2% | — | — | 412,000 | 84 |
| **Combined** | **Ecosystem** | **37,598** | **16,739** | **44.5%** | **1,713,096** | **1,288,706** | **797,951** | **239** |

*Living Work Delivery:* **6,929 closed beads** (out of 7,630 total) across 1,015 plans and 5,383 phases.

---

## 4. Multi-Format Output Design

### 4.1 Human Interactive View (Rich Terminal Dashboard)
```text
╭─ Project Stats · sase (+sase) · 8.0 months active (since 2026-02-14) ─────────╮
│                                                                               │
│  COMMITS          AGENT RATIO       SOURCE CODE       TEST CODE     BEADS     │
│  37,598 total     16,739 (44.5%)    1.71M lines       1.29M lines   6,929 cl. │
│  239 active days  cadence: 68/day   Python, Rust      1.09:1 ratio  7,630 tot │
│                                                                               │
╰───────────────────────────────────────────────────────────────────────────────╯
╭─ Repository Breakdown ────────────────────────────────────────────────────────╮
│ REPOSITORY   KIND     COMMITS    AGENT %   SOURCE LOC   TEST LOC   DOCS LOC   │
│ ───────────────────────────────────────────────────────────────────────────── │
│ sase         primary   16,181     41.9%    1,183,464   1,288,706     97,639   │
│ sase-core    linked     1,563     56.7%      529,632           -      5,702   │
│ plans        sidecar    9,456     75.5%            -           -    184,210   │
│ research     sidecar    2,064     93.6%            -           -     98,400   │
│ agents       sidecar    8,334      0.2%            -           -    412,000   │
│ sase-github  linked       [not cloned in current workspace]                   │
│ ───────────────────────────────────────────────────────────────────────────── │
│ TOTAL                  37,598     44.5%    1,713,096   1,288,706    797,951   │
╰───────────────────────────────────────────────────────────────────────────────╯
╭─ Work & Autonomy ─────────────────────────────────────────────────────────────╮
│ Beads: 6,929 Closed · 484 Ready · 207 In Progress · 9 Open (Total: 7,630)     │
│ Velocity: 16,739 agent-delivered commits · 8,334 archived agent sessions       │
╰───────────────────────────────────────────────────────────────────────────────╯
```

### 4.2 Machine Formats
- **JSON (`--json` / `-j`):** Strict Schema Version 1 payload with typed integers, ISO timestamps, and nested breakdowns for repos, languages, beads, and autonomy ratios (ready for agent consumption and CI regression tests).
- **Markdown (`--markdown` / `-m`):** Clean, ready-to-publish GitHub-Flavored Markdown tables and summary blockquotes for READMEs and PR descriptions.
- **Launch Post / Brief Summary (`--summary` / `-s`):** Curated bulleted metrics formatted for blog drafts, HN submissions, and release notes.

---

## 5. Architectural & Technical Implementation

1. **Rust Core vs. Python Host Split:**
   - Adhering to the `rust_core_backend_boundary`, reuse existing pure-Rust helpers in `sase_core_rs`:
     - `parse_commit_footer`: Parses `SASE_AGENT` and `SASE_TYPE` tags.
     - `parse_git_log`: Formatted commit timeline parsing.
     - `rust_beads.stats`: Fast SQLite bead database querying.
   - Python owns process execution (`git`, `tokei`), `RepoInventory` collection, and `rich` terminal rendering.
2. **Speed & Caching:**
   - Git commit counts and active dates are queried via `git rev-list --count` and `git log --grep="SASE_AGENT="` (~0.9s).
   - Line counts are powered by `tokei --output json` (~0.5s), with a streaming `git ls-files` fallback when `tokei` is absent.
   - Composite SHA caching stored in `~/.sase/projects/<key>/stats_cache.json` enables instant (<50ms) subsequent executions when repository `HEAD`s are unchanged.

---

## 6. Registration Verification

```bash
sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_project_stats_command_design__gem.md" -l "research:202610/sase_project_stats_command_design__gem.md"
```
- **Exit Status:** Succeeded (Code 0).
- **Artifact ID:** `explicit:8f6ad097e6ba24d20e840d24`
- **Resolution Status:** Exact live match verified in the artifact index.

The finalizer declaration has been submitted and accepted:

- **Instance**: `commit`
- **Repository**: `sdd:research` (`repo-736e4b0000d3`)
- **Action**: `commit`
- **Message**: `docs(research): add sase project stats command design report`
- **Status**: Declaration accepted. The host will commit the declared repository work upon turn completion.
