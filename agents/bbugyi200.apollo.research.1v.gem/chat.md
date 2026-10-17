# Chat History - ace-run (research.1v.gem)

- **TIMESTAMP:** 2026-10-16 21:43:31 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1v.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_213202.md`

## Prompt

%id(gem, clan=research.1v)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.1v.cdx`, `research.1v.cld`, `research.1v.grk`, `research.1v.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research on gascity (see the https://github.com/gastownhall/gascity
GitHub repo)? What is it used for? What is the long-term vision (if any) for this
project? 
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

# Research Report: Gas City (`gastownhall/gascity`)

**Researcher:** `research.1v.gem` (Swarm Member `gem`)  
**Report File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/gascity_architecture_use_cases_and_vision__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/gascity_architecture_use_cases_and_vision__gem.md)  
**Artifact Reference:** `file:explicit:2f76ccc5a57d987146dc6808` (`research:202610/gascity_architecture_use_cases_and_vision__gem.md`)

---

## Executive Summary

**Gas City (`gc`)** is an orchestration-builder SDK and execution runtime written in Go, developed under the `gastownhall` organization (primarily led by Julian Knutsen). It extracts and generalizes the multi-agent orchestration infrastructure from Steve Yegge’s seminal **Gas Town** (`steveyegge/gastown`) into a modular, role-agnostic foundation.

Where Gas Town proved the viability of multi-agent coding swarms on complex codebases but hardcoded specific roles (e.g., Mayor, Deacon, Polecat, Crew, Witness) directly into Go application code, Gas City enforces a strict design principle: **ZERO hardcoded roles** (*"If a line of Go references a specific role name, it's a bug"*). All agent roles, prompt behaviors, workflow graphs, and schedules are defined purely as configuration (**Packs**), while the Go runtime acts strictly as the neutral infrastructure substrate (supervision, process lifecycle, persistence, and event delivery).

---

## What is Gas City Used For?

Gas City addresses the bottleneck of single-agent, session-bound pair programming (such as sitting in a single terminal with Claude Code, Cursor, or Aider). Instead of requiring a human to babysit and prompt an agent sequentially, Gas City provides an autonomous, unattended software factory:

1. **Autonomous Fleet Orchestration (Formulas v2):**
   - Complex engineering initiatives (such as repository migrations, multi-step refactorings, or whole-feature builds) are authored as declarative **Formulas** (`*.formula.toml`).
   - The formula compiler materializes this workflow into an execution graph of **Beads** (work beads for agents and control beads for gates, retries, fan-out, and convoy drains).
   - The central controller runs this graph **outside the user’s session**, fanning tasks out in parallel across pools of coding agents (running in isolated git worktrees), enforcing dependencies, and driving the graph to completion.

2. **Durable, Crash-Resilient Work Tracking (Beads & NDI):**
   - Employs the **Non-Destructive Interaction (NDI)** principle: *all work is persistent in beads*.
   - If an agent crashes, stalls, or hits token limits, the session is disposable; the open bead remains in the store, and a fresh or recycled agent session resumes the task.

3. **Multi-Project / Multi-Repository Engineering (Rigs):**
   - Coordinates fleets across multiple separate repositories (**Rigs**) registered with the city (`gc rig add`), maintaining isolated bead namespaces and agent scopes.

4. **Continuous Maintenance & SRE Operations (Orders & Health Patrol):**
   - Automated triggers (**Orders** via cron, cooldown, events, or shell conditions) run unattended housekeeping, such as automated flaky test triage, dependency updates, and security patches.
   - Built-in **Health Patrol** monitors agent liveness, detects deadlocks or silent hangs, and executes backoff restarts with event alerts.

5. **Meta-Orchestration Platform:**
   - Functions as an engine to build any multi-agent topology via shareable configuration packs: Gas Town, Ralph-style loops, Anthropic Claude Code Agent Teams, or proprietary internal workflows.

---

## Core Architecture: The Six Primitives

Gas City decomposes all multi-agent software engineering into **six atomic primitives**:

| Primitive | Role | Description |
| :--- | :--- | :--- |
| **Agent** | **WHO** | Configured worker defined by a prompt template, runtime provider, and scope. Scalable into elastic pools. |
| **Bead** | **WHAT** | Universal persistence substrate. Tasks, inter-agent mail, convoys, waits, and epics are all beads differing only by `type`. |
| **Formula** | **HOW** | Reusable workflow method compiled into an executable dependency graph of work and control beads. |
| **Rig** | **WHERE** | An external project directory/repository registered with the city, providing bead namespace isolation. |
| **Pack** | **CONFIGURES** | Reusable package (`pack.toml`) declaring agents, formulas, orders, and prompts. The local city is the root pack (`city.toml`). |
| **Event** | **OBSERVE** | Immutable, append-only notification stream (`.gc/events.jsonl`, SSE, and CLI feed) fired reactively on all system transitions. |

### Architectural Invariants:
- **Zero Framework Cognition (ZFC):** Go source code handles transport, process supervision, and persistence, but never cognitive judgment. All reasoning remains in prompts and LLM inference.
- **The Bitter Lesson Filter:** Any proposed primitive must become *more* useful as frontier models improve, not less. Heuristic decision trees and hardcoded tool registries are explicitly rejected.
- **Pluggable Session Runtimes:** Supports `tmux` (default local interactive), `subprocess`, `exec`, `k8s` (Kubernetes pods), and `acp` (Agent Client Protocol).

---

## Long-Term Vision for Gas City

Based on architectural specifications, design proposals (`engdocs/`), roadmaps, and ongoing migrations, the project's long-term vision focuses on five key pillars:

1. **Hosted Gas City Cloud Platform ("Crucible" / `gascity.com`):**
   - Following the "Git to GitHub" model: the open-source `gc` binary remains commercial-free and protocol-agnostic, while `gascity.com` provides cloud infrastructure.
   - **Three-tier onboarding vision:**
     - *Flow 0 (Web Playground):* Instant, zero-install "Run this" button executing formulas on ephemeral cloud runners with live web-watch pages.
     - *Flow 1 (`gc init --at gascity.com`):* One-command CLI provisioning of hosted cloud cities with web dashboards and remote storage.
     - *Flow 2 (`gc run --at`):* Serverless, on-demand formula execution with managed cloud sandboxes and inference egress.
2. **Keyed Reconciler v2:**
   - Transitioning from legacy tick-based polling to an Erlang/OTP-grade event-driven session reconciler (`reconciler-v2`), guaranteeing automatic convergence to desired state after host reboots, crashes, or network disconnects.
3. **Dual-Tier Storage Architecture:**
   - Splitting storage classes to eliminate contention: **Dolt (`bd`)** for versioned, auditable work domain beads, and **local SQLite** for high-frequency ephemeral infrastructure beads (session tracking, wisps, and waits).
4. **Decentralized Workflow Ecosystem (`packman`):**
   - Establishing `registry.gascity.com` as a package registry for multi-agent workflows, enabling teams to publish, discover, and compose version-pinned engineering packs.
5. **Cloud-Native Fleet Infrastructure (Kubernetes & ACP):**
   - Scaling beyond single-machine developer setups to distributed Kubernetes clusters (`internal/runtime/k8s`) and standardizing on the **Agent Client Protocol (ACP)** to remain model- and harness-agnostic.

---

## Artifact Registration Details

The complete research report has been written and registered as a durable SASE snapshot:

- **Source Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/gascity_architecture_use_cases_and_vision__gem.md`
- **Artifact Label:** `research:202610/gascity_architecture_use_cases_and_vision__gem.md`
- **Artifact ID:** `explicit:2f76ccc5a57d987146dc6808`
- **Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261016213208/gascity_architecture_use_cases_and_vision__gem-07b2dba4c0f3.md`
- **Finalizer Declaration:** Submitted and accepted (`builtin@commit`).
