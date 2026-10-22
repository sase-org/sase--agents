# Chat History - ace-run (research.2r.gem)

- **TIMESTAMP:** 2026-09-27 11:32:53 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2r.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_111456.md`

## Prompt

%id(gem, clan=research.2r)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2r.cdx`, `research.2r.cld`, `research.2r.grk`, `research.2r.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
- Review the goal_outcomes_and_verification.md file in the research sidecar repo before
  performing your own research. My thoughts on this research from what I read:
  - I like that outcomes are embraced as a primary value-add for this functionality but
    am worried that we did not focus enough on user experience. For example, how do I
    figure out, for a particular sase project, which goals are currently active? Once
    I've found that goal, how do I then jump to any artifact (including a running agent)
    that is linked with that goal?
  - I'm worried that we are not letting agents set their own goals. I might be wrong
    about this, but doesn't that mean that users would always need to set the goal
    explicitly? That doesn't sound like a good design, if so, since it adds an extra
    burden on the user crafting the prompt.
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

# Research Synthesis: SASE Goals Architecture, UX, and Verification Design

**Author:** Researcher `gem` (5-Researcher Swarm)  
**Report File:** [`goals_architecture_ux_and_verification__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/goals_architecture_ux_and_verification__gem.md)  
**Artifact Reference:** `file:explicit:eb9a09a6eb40268bde2996ea` (`research:202609/goals_architecture_ux_and_verification__gem.md`)  

---

### Executive Overview

Moving SASE from **process-centric orchestration** (agent turns, stitches, subprocess lifecycles) to **outcome-centric software engineering** (goals, claims, evidence, and human verification) is an essential evolution. It directly solves the acute **notification fatigue** problem where intermediate agent completions (planners, individual epic phases, retry agents) bombard the operator with unread pings that do not signify a finished human outcome.

The independent research report has been completed, written to disk without overwrite, and registered as a durable SASE artifact. Below is the executive synthesis of the findings, architectural critiques, and recommended solution.

---

### 1. Critique of the Initial Plan & Key Corrections

#### A. Host-Owned Launch Invariant vs. Agent-Side `SASE_PLAN` Check
* **User Idea:** Require agents to check `SASE_PLAN` on turn 1 and call a `/sase_new_goal` skill if unset.
* **Critique & Flaws:**
  1. *Violation of Host-Owned Invariants:* In SASE, core system invariants must fail closed at the host boundary (following Decision `host-owned-completion`). Delegating the invariant *"all agents MUST have a goal"* to an LLM remembering to inspect an environment variable and call a skill on turn 1 will fail whenever an agent rushes to answer, forgets, or faces prompt pressure.
  2. *Swarm Race Conditions:* In a 5-researcher swarm launched from a single prompt, 5 parallel agents start without a plan. If each runs `/sase_new_goal`, 5 duplicate goals will be created simultaneously for the same user prompt.
  3. *Environment Hygiene:* In [`src/sase/agent/launch_spawn.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/agent/launch_spawn.py), `_remove_inherited_sase_plan_env()` deliberately scrubs `SASE_PLAN` to prevent ambient plan leakage across workspace boundaries. `SASE_PLAN` is a commit tag, not a runtime goal identifier.
* **Correction:** The host launcher must own goal establishment at spawn time. Before invoking the model, the host establishes the goal binding, records prompt provenance, and injects `SASE_GOAL_ID=<id>` into the environment and system instructions.

#### B. Planner Agents Are Not Exempt
* **User Idea:** Exempt planner agents from needing a goal.
* **Critique:** Planning *is* work with an explicit human intent (e.g., "Design architectural plan for auth refactor"). Exempting planners creates an unmonitored blind spot.
* **Correction:** Planners bind to the incoming request goal. When the planner completes, it submits its validated plan artifact (`plan:YYYYMM/name.md`) as evidence to satisfy the planning phase or transition the goal to active plan execution.

#### C. Zero User Prompting Burden with Full Agent Agency
* **User Concern:** *"I'm worried that we are not letting agents set their own goals... doesn't that mean that users would always need to set the goal explicitly?"*
* **Resolution:** There is zero extra user prompting burden. The user invokes SASE with standard natural language (`sase "fix redis timeout"` or `sase -m claude "explain rust core binding"`).
  - **Launch-Time Resolution:**
    1. *Plan-Bound Run:* Inherits the plan's mandatory `goal` string.
    2. *Bead-Bound Run:* Inherits the bead's title/intent.
    3. *Swarm/Fan-out:* All workers inherit the parent's unified goal.
    4. *Ad-Hoc Prompt:* Derived directly from the content-addressed [`submitted_xprompt.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/axe/run_agent_runner_setup_prompt.py).
  - **Agent Agency & In-Turn Refinement:** Once running, the agent can call `sase goal update` to refine the goal title, decompose the goal into sub-goals, or record structured acceptance criteria. The agent has agency, but never starts unmoored.

---

### 2. Core Domain Model & Lifecycle

The domain model lives in `sase_core` ([`crates/sase_core/src/goal/`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/linked/sase-core/crates/sase_core/src/finalizer/wire.rs)) to enforce the Rust backend boundary:

```text
                 ┌─────────────────────────────────────────────────┐
                 │                     Active                      │
                 │        (Agent(s) actively working)              │
                 └──────────────┬─────────────────────────▲────────┘
                                │                         │
                   builtin@goal │                         │ Reject claim
                     submission │                         │ (with feedback)
                      (action:  │                         │
                       "close") │                         │
                                ▼                         │
                 ┌────────────────────────────────────────┴────────┐
                 │                  Needs Review                   │
                 │       (Emits JumpToGoal notification to user)   │
                 └───────┬────────────────────────┬────────────────┘
                         │                        │
            Human clicks │           Human clicks │
             [v] Verify  │             [w] Waive  │
                         ▼                        ▼
                 ┌───────────────┐        ┌───────────────┐
                 │   Verified    │        │    Waived     │
                 │ (Cold Archive)│        │ (Cold Archive)│
                 └───────────────┘        └───────────────┘
```

- **`Active`:** In-progress work. Turns returning `keep_open` remain active and silent.
- **`Needs Review`:** An agent submitted `close` with host-validated evidence. Emits **`JumpToGoal`** attention to the user.
- **`Verified` / `Waived`:** Settled by the human operator. Moved immediately to cold storage.
- **`Rejected`:** Human sends feedback; goal reverts to `Active` for rework.

---

### 3. Closure Evidence & The `builtin@goal` Finalizer Contract

In [`src/sase/default_config.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/default_config.yml), `builtin@goal` is configured as a required finalizer running **after** `builtin@commit`:
- **Code Changes:** Requires a host-verified `stitch` reference (`$CURRENT_COMMIT`) + clean check receipt (`receipt:just-check-pass`). Uncorroborated prose ("I tested it and it works") is rejected by the host.
- **Research / Documentation:** Requires a registered durable artifact reference (`research:YYYYMM/...` or `file:...`).
- **Plan Delivery:** Requires a validated archived `plan:` reference.
- **Answer / Question:** Requires an audited transcript or captured response artifact.
- **Mandatory Human Verification Hint:** Every `close` submission must include an actionable, concise (under 60s) instruction for the human (e.g., *"Run `cargo test -p auth` and verify RS256 token rejection"*).

---

### 4. Attention & Notification Redesign

* **Silencing Intermediate Turns:** Normal agent completions with `keep_open` no longer emit `JumpToAgent` unread pings or chimes.
* **Notifying on Outcomes:** Only when an agent submits a `close` claim does the host dispatch a high-priority **`JumpToGoal`** notification.
* **Top-Bar Attention Indicator:** SASE ACE displays `🎯 <N> to verify` in the header bar whenever claims await review.
* **Preserving Failure Visibility:** Crashes, execution errors, interactive gates (`GateTurn`), and question prompts continue to alert immediately.

---

### 5. Intuitive & Beautiful TUI Experience

We design a **Dual-Surface Experience** matching the Textual styling guidelines in [`sase/memory/tui.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/memory/tui.md):

```text
 ┌────────────────────────────────────────────────────────────────────────┐
 │ SASE ACE  [Agents]  [Artifacts]  [Services]       🎯 2 to verify   09:41│
 ├────────────────────────────────────────────────────────────────────────┤
 │ [1 Agents] [2 Stitches] [3 Patches] [4 Beads] [5 Goals] [6 Plans]      │
 │                                                                        │
 │  ╭─ Needs Review (2 claims awaiting human verification) ─────────────╮ │
 │  │ STATUS   GOAL / CLAIM               CONTRIBUTORS  EVIDENCE   TIME │ │
 │  │ ◉ REVIEW Add RS256 JWT auth         3 agents      1 stitch   2m   │ │
 │  │          ↳ Claim: Passed cargo test; token validation functional  │ │
 │  │          ↳ Hint: Run `cargo test -p auth` (Press [v] to verify)   │ │
 │  │ ◉ REVIEW Research Goals TUI UX      5 agents (gem) 1 report  12m  │ │
 │  │          ↳ Hint: Inspect section 5 in research report             │ │
 │  ╰───────────────────────────────────────────────────────────────────╯ │
 │  ╭─ In Progress (3 active goals) ────────────────────────────────────╮ │
 │  │ STATUS   GOAL TITLE                 CONTRIBUTORS  PLAN/BEAD  TIME │ │
 │  │ ◈ ACTIVE Fix Redis timeout under load  1 agent    bead:142    8m  │ │
 │  │ ◈ ACTIVE Refactor tool control plane  2 agents    plan:09/tcp 45m │ │
 │  │ ◈ ACTIVE Implement Lumberjack chop    1 agent    —          1h12m │ │
 │  ╰───────────────────────────────────────────────────────────────────╯ │
 ├────────────────────────────────────────────────────────────────────────┤
 │ [v] Verify   [w] Waive   [r] Reject & Reopen   [Enter] Inspect Details │
 └────────────────────────────────────────────────────────────────────────┘
```

1. **Artifacts > Goals Pane (`5` or `g`):** The project-wide control room. Split into **Needs Review** (warm amber `[bold #FFAF00]`) and **In Progress** (calm teal `[#00D7AF]`). Pressing `Enter` opens the goal inspector with the original launch prompt, evidence links, and contributor roster.
2. **Agents Tab Integration:**
   - Every agent row displays a compact goal chip: `🎯 [jwt-auth]`.
   - Pressing `Shift+G` on the Agents tab toggles grouping `by goal`, clustering collaborating agents under a single outcome banner.
3. **Artifact Link Graph Jumps:**
   - The closed relation registry ([`docs/artifact_links.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/docs/artifact_links.md)) is extended with `pursues` (Agent $\leftrightarrow$ Goal), `evidences` (Artifact $\leftrightarrow$ Goal), and `defines` (Plan $\leftrightarrow$ Goal).
   - Selecting a contributor in the Goals pane and pressing `Enter` jumps directly to that agent on the Agents tab (`JumpToAgent`).
   - Selecting a goal chip on the Agents tab jumps directly to that goal in the Goals pane.

---

### 6. Distributed Storage & Strict $O(n_{\text{unsettled}})$ Performance

To guarantee that thousands of settled goals have zero impact on foreground performance:
1. **Physical Directory Partitioning in `agents` Sidecar:**
   - `goals/active/`: Stores *only* unsettled goals (`Active` and `Needs Review`). In normal project operation, $n \approx 5\text{--}50$.
   - `goals/settled/YYYYMM/`: Cold historical archive. Settled files are moved here atomically upon human verification.
2. **Materialized Hot Projection (`active_goals.json`):**
   - A single compact JSON file on disk maintained by the host.
   - Foreground listing reads **one small file** ($\approx 20\text{--}40$ KB). Query latency is strictly under **1 millisecond**.
3. **Cross-Machine Sync:**
   - Follows Decision `machine-link-writes-off-primary`: mutations commit to the host-owned machine lane and auto-sync via Git tracking branches with optimistic revision counters and sync watermarks.

---

### Verification and Report Artifact

The full technical design and architectural analysis is available in the registered artifact:
- **Local Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/goals_architecture_ux_and_verification__gem.md`
- **Artifact Ref:** `file:explicit:eb9a09a6eb40268bde2996ea`
- **Artifact Label:** `research:202609/goals_architecture_ux_and_verification__gem.md`
- **Host Declaration:** Submitted and accepted (`Accepted final declaration for: commit`).
