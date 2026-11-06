# Chat History - ace-run (research.2p.gem)

- **TIMESTAMP:** 2026-10-27 13:40:07 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2p.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261027_132548.md`

## Prompt

%id(gem, clan=research.2p)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2p.cdx`, `research.2p.cld`, `research.2p.grk`, `research.2p.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support to sase for detailed usage tracking somehow.

- We will need to make sure this doesn't hurt performance too much (the TUI is already
  too slow, for example).
- The goal of this change is to help me understand which parts of sase I never use.
  After a month or two of monitored use, for example, I would like to go through this
  data and use it to help me find functionality that should be deleted.
- We will eventually want to support allowing external users to opt-in to periodically
  packaging up this usage data and sending it to one of my servers for analysis, so it
  is important that we don't store any sensitive data.
- I will need some way to visualize my usage of sase after I have enough data. Think
  hard about what the best UX for this functionality looks like.
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

# Research Report Completed: Feature Usage Telemetry & Dead-Code Pruning in SASE

**Researcher:** `research.2p.gem`  
**Report File:** [`feature_usage_tracking_and_pruning_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/feature_usage_tracking_and_pruning_design__gem.md)  
**Registered Artifact:** `research:202610/feature_usage_tracking_and_pruning_design__gem.md` (`file:explicit:ce90d8c7fd829546970b6f5a`)

---

## Executive Summary of Findings & Critique

### 1. Critique of the Plan: Is Telemetry-Driven Deletion a Good Idea?
Pruning dead code across SASE is urgent—the system has accumulated over 60 top-level CLI commands, hundreds of TUI widgets, complex macro workflows, and legacy compatibility adapters that directly drive TUI slowness and maintenance debt. However, using raw usage counts over a 30-to-60 day observation window as an autonomous deletion trigger is dangerous:

1. **The "Chesterton's Fence" of Low-Frequency vs. Zero-Value Utilities**:
   - Disaster recovery, emergency rollbacks, and diagnostic tools (e.g. `sase doctor`, `sase ace restore`, `revert_agent_workspace`, `cleanup-test-data`) are rarely used in smooth daily operations. You might not use an emergency exit for 90 days, but deleting it because count equals zero causes catastrophic failure during an incident.
   - Lifecycle, bootstrap, and migration tools (`sase init`, `repo init`, `sase migrate`) run once per repo or setup; their frequency is near zero by design.
2. **Discoverability vs. Utility**:
   - Zero invocations often indicate poor ergonomics, missing keybinding hints, or awkward syntax rather than lack of value. Deleting an underused feature without investigating *why* it was unused removes functionality that may only need a discoverability fix.
3. **The Solo-User Persona Bias**:
   - Bryan's daily workflow (heavy swarm automation, specific TUI habits, print-mode commands) represents one profile. Deleting features based solely on one user's 60-day habits risks breaking multi-agent workflows, secondary machines (Apollo vs. Athena), or headless CI pipelines.
4. **Internal Code Bloat vs. Surface Features**:
   - True bloat is often hidden internal complexity (dead classes, abandoned compatibility shims like legacy `changespec` aliases, redundant layout recalculations). Usage telemetry cannot see internal dead code—it must be paired with static call-graph analysis (Symvision / `vulture`).

**Adjusted Requirement (The 4-Tier Pruning Lifecycle)**:
Instead of immediate deletion, telemetry must feed a structured triage pipeline:
- **Protected / Recovery**: Exempt from pruning (`doctor`, `restore`, `init`).
- **Core Workflow**: Active daily tools (>5 uses/month).
- **Experimental / Incubating**: Features under evaluation (<2 uses/month).
- **Sunset Candidates**: Zero activity in 60 days. Enter the SASE Deprecation Pipeline by scaffolding a `sunset` feature flag (`sase flag new sunset_<id> -k sunset --remove-when "..."`). If no objections or invocations occur during the 30-day sunset window, the Off branch is deleted and the flag bead closed.

---

### 2. Naming Conflict Resolution: `sase usage` is Already Taken
In SASE, `sase usage` (`sase usage list`, `sase usage refresh`) and the glossary term `Usage Window` are exclusively dedicated to LLM provider subscription quota and rate-limit tracking. Reusing `sase usage` for feature telemetry creates CLI syntax collisions.
- **Recommended Taxonomy**:
  - Presentation & Triage: **`sase stats features`** (CLI) and the **Features Deck** in ACE Admin Center Statistics (aligning with `sase stats project` and `sase stats macro`).
  - Storage & Sync: **`sase telemetry features`** and **`sase telemetry export`** (aligning with `sase.telemetry` and SQLite metrics persistence).

---

### 3. Performance Architecture: Zero-Overhead Instrumentation
The October 2026 performance census (`tui_gc_measurement_20261023.md`) demonstrated that SASE's TUI already suffers from severe Python GC heap bloat and multi-second Gen-2 GC pauses (e.g. 2.76s idle p95 on Athena). Telemetry must not exacerbate this:
- **No Keystroke Telemetry**: Never track cursor movement, `j`/`k`, or text editing in `prompt_text_area`. Track only discrete *semantic user intents* (CLI subcommands, TUI tab switches, modal opens, macro expansions, skill calls). Volume is ~50–500 events/day.
- **Hot-Path Cost < 50 Nanoseconds**: Features are mapped to fixed indices in an immutable catalog. Recording is a preallocated integer array bump in memory (`_counts[idx] += 1`). Zero heap allocations, zero string formatting, zero disk I/O on the hot path.
- **Asynchronous, Pump-Free Persistence**:
  - CLI: Flushed during `atexit` (via `register_flush_on_exit`).
  - TUI: Flushed during quiet 15-minute idle ticks using `spawn_pump_free_task()`, or on clean `on_unmount`.
  - Storage: Rust core `sase_core_rs.telemetry_record_batch` writing to SQLite WAL with a 250ms busy timeout.

---

### 4. Privacy, Security & Opt-In Architecture
To safely support opt-in external telemetry uploads:
- **Strict Allowlist**: Only canonical Feature IDs (e.g. `cli:bead:list`), bucketed invocation counts (`0`, `1-4`, `5-19`, `20-49`, `50-99`, `100+`), day-level coarse timestamps, and coarse environment metadata (OS, SASE version, Python version, configured LLM providers).
- **Strict Denylist (NEVER Stored, NEVER Sent)**: Zero project names, zero file paths, zero repo URLs, zero branch names, zero prompt contents, zero bead titles, zero commit messages, zero freeform CLI arguments.
- **Strict Opt-In**: `telemetry.opt_in_sync: false` by default.
- **Dry-Run Inspection**: `sase telemetry export --inspect` prints the exact raw JSON for human inspection before transmission.

---

### 5. Beautiful & Intuitive UX Design
1. **CLI Dashboard (`sase stats features`)**:
   - Native Rich tables with Unicode block sparklines (` ▂▃▅▆▇█`), categorical color bars, and status pills (`🟢 Active`, `🟡 Occasional`, `💤 Dormant`, `💀 Candidate`).
   - Dedicated **`sase stats features --prune`** advisor mode ranking dead features by **Code Weight (LOC) × Dormancy Duration**, showing maximum ROI for code removal.
2. **ACE TUI "Features & Pruning" Deck (Admin Center)**:
   - Embedded directly in the TUI Statistics tab.
   - Dual-pane layout: Master feature list on the left; detailed code and usage inspector on the right.
   - Actionable single-keystroke shortcuts:
     - `d`: Propose a SASE `sunset` feature flag via `sase flag new`.
     - `b`: File a task bead for removal.
     - `x`: Toggle "Protected" status (with an auditable reason).
3. **Standalone Visual HTML/SVG Treemap (`sase stats features --html`)**:
   - Zero-dependency interactive treemap: Box Area = Lines of Code, Box Color = Usage Frequency.
   - Immediately visualizes where large chunks of dormant code are hiding.

---

## Artifact & Final Declaration Details

- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/feature_usage_tracking_and_pruning_design__gem.md`
- **Artifact Creation Command:**
  ```bash
  sase artifact create \
    -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/feature_usage_tracking_and_pruning_design__gem.md" \
    -l "research:202610/feature_usage_tracking_and_pruning_design__gem.md"
  ```
- **Artifact Reference:** `file:explicit:ce90d8c7fd829546970b6f5a`
- **SASE Finalizer Declaration:** Submitted and accepted for dirty obligation repository `sdd:research` (`repo-736e4b0000d3`). Ready for host commit completion.
