# Chat History - ace-run (research.1u.gem)

- **TIMESTAMP:** 2026-10-16 18:09:40 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1u.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_175332.md`

## Prompt

%id(gem, clan=research.1u)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.1u.cdx`, `research.1u.cld`, `research.1u.grk`, `research.1u.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with gastown (see the
https://github.com/gastownhall/gastown GitHub repo), with a particular focus on the
things that gastown does better than sase? End your analysis with a ranked list of ways
that gastown is superior to sase along with a (not necessarily one-to-one) ranked list
of recommended changes you think I should consider making to sase based on your report's
findings. 
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

# Comparative Research Report: SASE vs. Gas Town
**Researcher:** `gem` (Independent Research Swarm)  
**Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/gastown_vs_sase_comparative_analysis__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/gastown_vs_sase_comparative_analysis__gem.md)  
**Artifact Registration:** `research:202610/gastown_vs_sase_comparative_analysis__gem.md` (Artifact ID: `explicit:77f753077671f7a116272bfa`)

---

## Executive Summary

Both **SASE** and **Gas Town** (`gastown`, from [gastownhall/gastown](https://github.com/gastownhall/gastown)) address the problem of orchestrating teams of parallel AI coding agents (Claude Code, OpenAI Codex, GitHub Copilot, Gemini, Cursor, etc.) across software repositories. 

However, they diverge fundamentally in their underlying paradigm:
- **SASE** prioritizes **disciplined governance, human-in-the-loop terminal cockpit supervision, single-turn deterministic execution**, and host-owned completion. It models coding agents as strictly bounded, stateless workers executing explicit macro directives and memory bundles.
- **Gas Town** prioritizes **autonomous multi-agent society scaling, persistent identities, git worktree storage, relational state tracking via Dolt SQL**, and autonomous quality gating. It models the workspace as a living town where worker agents (**Polecats**) self-manage completion, communicate via asynchronous mail (`gt mail`), and are continuously monitored by a multi-tier watchdog hierarchy.

While SASE provides superior terminal ergonomics (`sase tui`, ACE Admin Center), memory compilation, and macro templating (`#xprompt`), **Gas Town is architecturally superior in several mission-critical areas of scale, persistence, automated quality gating, and multi-agent coordination**.

---

## Ranked List: Ways Gas Town is Superior to SASE

1. **Bors-Style Batch-then-Bisect Merge Queue (The Refinery)**  
   *Gas Town's most decisive advantage.* When multiple agents finish branches concurrently, the Refinery batches pending Merge Requests, constructs an ancestry-preserving rebase stack, and runs verification gates **once** on the stack tip. If green, all MRs fast-forward merge to `main`. If red, it retries for flakiness and performs binary bisection (`bisectBatch`) to pinpoint the exact culprit MR, automatically ejecting it and requesting rework while merging the healthy subset. SASE currently lacks an autonomous background batch-and-bisect merge queue daemon.

2. **Git Worktree Storage Engine vs. Full Repository Clones**  
   Gas Town uses `git worktree` based on a canonical clone (`mayor/rig`) for worker agents and the refinery. Spawning an agent is sub-second and shares the `.git` object store. SASE provisions ephemeral workspaces as full repository clones (`sase_<N>`), which imposes severe disk overhead (scaling $O(N \times \text{repo\_size})$) and provisioning latency.

3. **Relational Versioned State Store (Dolt SQL Server) vs. Flat File Beads**  
   Gas Town uses a centralized Dolt SQL Server (Git-for-data) per town on port 3307. All issues, dependencies, labels, messages, events, and interactions reside in relational SQL tables (`issues`, `dependencies`, etc.) with atomic `BEGIN` / `DOLT_COMMIT` / `COMMIT` discipline. This provides real relational joins, time-travel queries (`AS OF`), and zero git merge conflicts on issue state, compared to SASE's flat-file `.beads/` and SQLite caches.

4. **Live Predecessor Session Forking & Interrogation (`gt seance`)**  
   Rather than forcing successors or operators to parse massive static JSONL logs, `gt seance --talk <id> -p "..."` uses session forking (`claude --fork-session --resume <id>`) to dynamically spawn a live conversational instance of the predecessor's exact cognitive state. You can ask: *"Why did you make this architectural choice?"* or *"Where did you stash the intermediate files?"* with full prompt cache continuity.

5. **Multi-Tier Autonomous Supervision & Watchdog Chain (Daemon → Boot → Deacon → Witness → Dogs)**  
   Gas Town maintains a four-tier supervisory structure: a pure Go Daemon (3-minute heartbeat) that spawns Boot (an AI triage agent) if the Deacon is down; the Deacon (cross-rig AI supervisor); Witnesses (per-rig AI team leads); and Dogs (headless background maintenance workers). Paired with the Universal Propulsion Principle (GUPP, 30m inactivity timeout), it autonomously flags stalled agents, recovers abandoned beads, and cleans zombie sessions.

6. **The Mayor & MEOW (Conversational Town-Level Executive Coordinator)**  
   Operators interact directly with **The Mayor** (`gt mayor attach`). The Mayor maintains full context across all rigs, convoys, and agent states, breaking down high-level operator goals into convoys and beads, slinging them to workers, tracking progress, and synthesizing results. SASE requires more manual operator orchestration from the CLI or TUI.

7. **Formulas & Molecules Workflow Engine with Checkpoint Recovery**  
   Declarative TOML workflow DAGs support both lightweight *root-only wisps* (steps rendered inline at prime time to prevent DB row explosion) and *poured wisps* (steps materialized as sub-wisps). If an expensive workflow crashes, completed steps remain closed, allowing immediate resumption from the last checkpoint.

8. **Multi-Channel Escalation Engine with Time-Decay Severity Aging**  
   Blockers escalated via `gt escalate -s <CRITICAL|HIGH|MEDIUM>` route across beads, mail, email (SMTP), SMS webhooks, and Slack. `gt escalate stale` automatically bumps severity (`MEDIUM` → `HIGH` → `CRITICAL`) and escalates notification channels if human intervention is delayed.

9. **Native OpenTelemetry (OTEL) Export & Dual UI (TUI Feed + Web Dashboard)**  
   Emits structured OTLP metrics and logs to backends like VictoriaMetrics, Prometheus, or Grafana. The TUI feed features a dedicated "Problems View" (`gt feed --problems`) for instant health classification (`GUPP Violation`, `Stalled`, `Zombie`, `Working`, `Idle`), complemented by an htmx web dashboard (`gt dashboard`).

10. **Clean Ephemeral Scheduling Contexts with Circuit Breakers**  
    Gas Town decouples scheduling parameters from work items by storing dispatch state in ephemeral sling context beads (`gt:sling-context`). Work beads stay pristine, and built-in circuit breakers trip after 3 dispatch failures.

11. **Single Compiled Binary Distribution & Packaging Simplicity**  
    A single static Go binary (`gt`) embeds all templates, formulas, doctor checks, and default configs. It installs trivially via Homebrew, `go install`, npm, or Docker, avoiding SASE's multi-tier Python environment and Rust compilation pin dependencies.

---

## Ranked List: Recommended Changes for SASE

1. **[High Priority] Transition Ephemeral Workspaces from Full Clones to Git Worktrees**  
   - *Action*: Update SASE workspace provisioning to maintain a canonical hidden clone per project and spawn ephemeral agent workspaces via `git worktree add -b sase-worker/<id> <path>`. Share git object databases across all agent runs to achieve sub-second workspace provisioning and reduce disk footprint by 80–90%.

2. **[High Priority] Build an Autonomous Batch-and-Bisect Merge Queue Daemon ("SASE Refinery")**  
   - *Action*: Introduce a background merge queue service in `sase axe` or `sase mq`. Rebase ready agent patches into stacks, verify the tip via `just check`, fast-forward merge on green, and binary-bisect failing batches to isolate and reject the culprit while landing the passing subset.

3. **[High Priority] Introduce Dynamic Predecessor Session Interrogation (`sase seance`)**  
   - *Action*: Extend SASE provider adapters (specifically Claude Code and Codex) with a `/sase_seance` or `sase seance` command using `--fork-session --resume <id>`, allowing agents or humans to query completed agent turns conversationally.

4. **[Medium Priority] Implement Active Propulsion (GUPP) & Autonomous Health Supervision**  
   - *Action*: Add active stall detection to the SASE service host. If an active agent makes zero progress (no tool calls, no output) for 30 minutes, classify it as stalled and trigger an automated nudge or graceful turn termination to release the runner slot. Add a dedicated "Problems View" filter in `sase tui` with instant recovery shortcuts (`nudge`, `retry`, `abort`).

5. **[Medium Priority] Upgrade Beads & Work Tracking to an Embedded Relational Database (SQLite / Dolt)**  
   - *Action*: Replace flat `.beads/` files with an embedded relational store (SQLite with WAL mode or Dolt client bindings) to eliminate filesystem lock contention, avoid file merge conflicts, and provide indexed SQL queries and dependency rollups.

6. **[Medium Priority] Add Multi-Channel Escalation & Severity Aging to SASE Gates**  
   - *Action*: Enhance `sase gate` to support configurable webhook routes (Slack, email, SMS) and automated severity escalation when gates remain unanswered past configured thresholds.

7. **[Medium Priority] Implement Checkpointed Multi-Step Workflow DAGs (Molecules / Poured Wisps)**  
   - *Action*: Extend SASE macros into formal workflow DAGs with step dependencies (`needs = [...]`) and step-level checkpointing, allowing interrupted multi-stage workflows to resume from the last successful step.

8. **[Low Priority] Export Native OpenTelemetry (OTEL) Metrics & Tracing**  
   - *Action*: Instrument the SASE runner and core lifecycle events with OpenTelemetry standards, allowing fleet operators to export metrics (session duration, tool latencies, token consumption) to enterprise collectors (VictoriaMetrics, Datadog, Prometheus).

9. **[Low Priority] Provide an Optional Headless Web Status Dashboard**  
   - *Action*: Add an optional lightweight web status server (`sase dashboard`) providing non-terminal stakeholders with real-time visibility into active agent sessions, patches, and queue health.

---

### Verification and Persistence Evidence
- **Report Written**: [`sase/repos/research/202610/gastown_vs_sase_comparative_analysis__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/gastown_vs_sase_comparative_analysis__gem.md) (16,983 bytes)
- **Artifact Registered**: `sase artifact create` succeeded with ID `explicit:77f753077671f7a116272bfa`, label `research:202610/gastown_vs_sase_comparative_analysis__gem.md`.
- **Final Declaration**: Host-owned final declaration submitted and accepted (`sase final submit`).
