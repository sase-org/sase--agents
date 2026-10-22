# Chat History - ace-run (research.2m.gem)

- **TIMESTAMP:** 2026-09-26 12:52:12 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2m.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_123905.md`

## Prompt

%id(gem, clan=research.2m)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2m.cdx`, `research.2m.grk`, `research.2m.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
"Goals" functionality to sase.

- Goals should be associated with the original prompts that were used to launch the sase
  agent that created the goal.
- All sase agents MUST have a goal defined.
  - We already support a required `goal` field for tale / epic plans, so these should be
    used as an agent's goal whenever a plan file is associated with that agent.
  - Any sase agent that does not have a goal associated with it implicitly through a
    plan should be required to create a new goal or, ideally, link to an existing active
    goal.
  - One idea for implementing this would be to require that every sase agent that is NOT
    tasked with creating a plan using the /sase_plan skill (i.e. planner agents don't
    need to do this) check if the `SASE_PLAN` environment variable is set at the start
    of EVERY conversation. If not, it could invoke a new /sase_new_goal xprompt skill.
    This is just one thought, though. Think hard about the best way to solve this.
  - An example goal for an agent without an associated plan that couldn't find a related
    goal to link to might be to answer a user question.
- We should use a new finalizer that requires sase agents to explicitly decide whether
  or not to close the goal or leave it open. An agent that chooses to close a goal must
  provide evidence to the finalizer (that will then be linked to the goal somehow before
  closing it). Think hard about what we should require this evidence to be.
- The TUI should have a new "Goals" panel somewhere that users can use to see all active
  goals for a project. We should use artifact links to make it very easy for users to
  jump from this panel to any artifact and/or sase agent on the "Agents" tab linked to
  that goal.
- One motivation for this change is to start using newly done goals to notify me that I
  need to verify something. I currently use agent completion notifications for this,
  either directly or via the unread indicators on the agent tab. The problem with that
  approach is that not every agent that completes needs my attention like this (I really
  only need to be alerted when my agents claims that a goal which was set is now
  complete).
- The above requirements imply that sase agents need access to all active goals (really,
  any human/agent working on a sase project from any machine needs this access). This
  access needs to be lightning fast. More specifically, we should aim for `O(n)`
  performance, where `n` is the number of active goals (so done goals have no effect on
  performance).
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

# SASE Goals Capability: Architectural Research, Critique & Design Report

**Researcher:** `research.2m.gem`  
**Report Artifact:** `research:202609/sase_goals_architecture_and_design__gem.md`  
**Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/sase_goals_architecture_and_design__gem.md`  
**Durable Artifact Ref:** `file:explicit:42d6f1a0c786ef0fb0c21b66`  

---

## 1. Executive Summary & Strategic Critique

### Is Adding "Goals" to SASE a Good Idea?
**Yes, the core motivation is exceptionally strong.** 

Currently, SASE suffers from **notification fatigue and semantic fragmentation**:
1. **Notification Noise:** SASE alerts the user whenever *any* agent turn finishes (`notify_workflow_complete` / `_unread_completed_agent_ids`). In complex workflows (epics, swarms, replans, gate handoffs), 80–90% of completing agents are intermediate workers. Alerting on each one creates alert blindness.
2. **Missing Outcome Boundary:** While SASE plans have a required `goal` field in frontmatter, ad-hoc agent runs launched from prompts have no structured contract defining *"What concrete outcome must be true for the work to be considered complete?"*

Introducing **Goals** as a first-class operational entity bridges the semantic gap between high-level human intent (the prompt) and low-level agent turns, while transforming SASE's notification model into a **verification-first attention system**.

---

## 2. Critique of Proposed Implementation Details & Required Adjustments

While the intent is sound, several of the initial implementation ideas present serious architectural friction:

### 1. Reject Agent-Side Runtime Goal Discovery (`/sase_new_goal` checked every turn)
* **The Proposal:** Every non-planner agent checks if `$SASE_PLAN` is set at the start of *every* conversation; if not, it invokes a new `/sase_new_goal` skill to discover or create a goal.
* **Why this is problematic:**
  * Violates SASE's `single-turn-agents` invariant ("continuation is always mechanical, never a promise to resume").
  * Wastes prompt tokens and 1–2 expensive LLM tool-calling roundtrips before starting actual work.
  * LLMs frequently hallucinate or choose inappropriate existing goals when matching fuzzy text.
* **Recommended Adjustment (Host-Owned Goal Resolution):**
  * The SASE host launcher (`sase run`, `sase bead work`, TUI prompt bar) **already possesses the prompt, plan, and bead context before the agent process is spawned**.
  * The host resolves or instantiates the Goal deterministically at launch time and injects `SASE_GOAL_ID`, `SASE_GOAL_TITLE`, and `SASE_GOAL_OBJECTIVE` directly into the agent's environment and `agent_meta.json`. The agent starts work immediately with zero discovery overhead.

### 2. Planner Agents Must Also Have Goals
* **The Proposal:** Planner agents are exempt from having goals.
* **Why this is problematic:** Creating a plan is itself a critical, high-leverage objective. If planners are exempt, the goal tracking system is blind during design.
* **Recommended Adjustment:** Planners are assigned a Goal whose objective is *"Formulate and validate approved plan for <intent>"*. When the plan is approved, that planning goal closes, and the downstream implementation goal is automatically initialized from `plan.goal`.

### 3. Separation of Concerns: Goals vs. Beads
* Goals must **not** simply be another bead subtype (`task(goal)`). Beads represent schedulable issues with complex triage, dependencies, and +1 corroboration.
* Goals represent **Intent & Desired Outcome**. A Goal binds to Prompts, Plans, Beads, and Agents through SASE's typed **Artifact Links** (`implements`, `cites`, `achieved-by`).

---

## 3. High-Performance $O(n)$ Storage Architecture

The requirement dictates that querying all active goals must be **lightning fast and strictly $O(n)$**, where $n$ is the count of active goals, so historical completed goals have zero impact.

### Two-Bucket State Partitioning
Instead of an append-only monolithic file (which degrades to $O(N)$ across all history), storage is partitioned into two distinct directories in a dedicated sidecar or git repository (`sase/repos/goals/`):

```
sase/repos/goals/
├── active/
│   ├── g-260926-a1b2.json
│   ├── g-260926-c3d4.json
│   └── g-260926-e5f6.json
└── archive/
    └── 202609/
        ├── g-260925-0012.json
        └── g-260926-9876.json
```

1. **Strict $O(n)$ Listing:** Reading active goals is simply `readdir("active")`. Because completed goals are moved to `archive/`, the directory contains only $n$ files (typically 1–20). Reading 10 small JSON files takes **< 1 millisecond**.
2. **Zero-Merge-Conflict Multi-Machine Concurrency:** Each active goal is an independent file (`<id>.json`). Multiple machines or parallel workspaces adding goals concurrently commit separate files to git without merge conflicts.
3. **Atomic Closure:** Closing a goal performs an atomic move:
   `git mv active/<id>.json archive/<YYYYMM>/<id>.json`

---

## 4. The Goal Finalizer & The Evidence Triad

### The `builtin@goal` Finalizer
Alongside `builtin@commit`, SASE introduces `builtin@goal`. In `sase final context -f json`, every agent carrying `SASE_GOAL_ID` receives a Goal obligation.

In its final manifest, the agent must submit:
* `action: "keep"`: The turn finished intermediate work (e.g. Phase 1 of an Epic). The goal remains active. **No user alert is sent.**
* `action: "close"`: The agent claims the goal is complete and **must provide the Evidence Triad**.

### The Evidence Triad
To prevent premature or unproven closures, the host finalizer enforces three evidence pillars:
1. **Execution Witness:** The command executed during the turn proving correctness (e.g. `just check` or `pytest`), verified against `tool_calls.jsonl` to ensure it ran and exited with code `0`.
2. **Deliverable Artifacts:** Concrete artifact references created/modified (`stitch:<N>`, `file:explicit:<hash>`, `plan:202609/...`).
3. **Satisfaction Rationale:** 1–3 sentences stating what was verified and why the objective is met. Empty or generic placeholders are rejected.

Upon submission of a valid closure manifest, the host automatically registers typed artifact links:
```bash
sase artifact link add <evidence_ref> verifies goal:<goal_id> "<rationale>"
```

---

## 5. Notification & Attention Shift

* **Intermediate Agents (`keep`):** Logged silently to agent history. No audio chimes, no unread notification badges.
* **Goal Completed (`close`):** Triggers a high-priority **Goal Verification** notification:
  * Tagged `["goal", "verification-needed"]`.
  * Top Bar indicator shifts from unread agent counts to `🎯 1 to verify`.
  * The user is prompted to verify only when an actual outcome is ready.

---

## 6. Intuitive and Beautiful TUI Design

A dual-surface architecture keeps the UI clean, fast, and visually cohesive:

1. **The Primary Goals Pane (`Artifacts -> Goals` subtab):**
   * **Accent:** Vibrant Emerald (`#00D787`), Icon: `🎯`.
   * **Left Panel:** Active Goals list showing goal IDs, titles, status badges (`ACTIVE`, `VERIFYING`), elapsed runtimes, and active clan chips.
   * **Right Panel:** Rich Goal Detail Surface:
     * Full Objective and success criteria.
     * Collapsible Original Prompt block with syntax highlighting and `ph_` prompt link.
     * Associated Plan, Bead, and Clan links.
     * Completion Evidence drawer (witness command output, artifact chips).
     * One-key action buttons: `[V] Accept & Close`, `[R] Reject & Reopen`, `[J] Jump to Agent`.
2. **The Agents Tab Context Surface:**
   * **Goal Chip:** Displayed in the Agent Info Row for the currently selected agent.
   * **Goal Card:** A dedicated card in the Agent Detail Deck (Main Deck) showing the goal statement, prompt context, and progress milestones.
3. **Keyboard & Jump Hints:**
   * Full integration with SASE jump hints (`_node_jump.py`): press `j` in the Goals pane to jump directly to any active agent in the Agents tab, or jump to any evidence artifact in the pager.

---

## 7. Rust Core Backend Boundary (`sase-core`)

In accordance with SASE Rule 1.3 and Decision 18:
* **`sase_core::goal` (Rust):** Houses `GoalRecord`, `GoalStore`, the $O(n)$ active goal directory iterator, schema validation, and evidence verification.
* **`sase_core_py`:** Exposes PyO3 bindings.
* **`sase` (Python):** Contains CLI commands (`sase goal`), launch hook resolution, the `builtin@goal` finalizer, and the Textual TUI widgets.

---

## 8. Registration & Status

The full research report has been authored and registered into SASE's durable artifact storage:
* **Source:** `sase/repos/research/202609/sase_goals_architecture_and_design__gem.md`
* **Artifact Snapshot:** `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202609/sase_goals_architecture_and_design__gem.md" -l "research:202609/sase_goals_architecture_and_design__gem.md"`
* **Registration Ref:** `file:explicit:42d6f1a0c786ef0fb0c21b66`
* **Finalizer Declaration:** Submitted and accepted (`builtin@commit`).
