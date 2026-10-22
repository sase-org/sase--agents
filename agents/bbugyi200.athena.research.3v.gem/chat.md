# Chat History - ace-run (research.3v.gem)

- **TIMESTAMP:** 2026-10-06 16:59:15 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3v.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_163905.md`

## Prompt

%id(gem, clan=research.3v)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3v.cdx`, `research.3v.cld`, `research.3v.grk`, `research.3v.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add a `for_epic=<true|false>` keyword input to the `%wait` directive.

- This input would default to `true` when a sase agent name is provided as an argument
  alongside it (we should throw an error and/or show diagnostic warnings if a user
  attempts to use this input without an agent name) and will trigger a new behavior.
- Namely, when `for_epic=true`, the sase agent that is launched from that prompt should
  wait for the agent specified by the `%wait` directive AND should also wait for any
  epic bead that this agent may or may not create.
- In order to make this work reliably, we will probably need to make sure that
  artifact/bead links are established consistently from the sase agent that creates an
  epic bead to that epic bead. I think we already have the infrastructure set up for
  this.
- We will also want to make it very clear to the user in the TUI somehow when an agent
  has stopped waiting for the agent it specified via the `%wait` directive and is now
  waiting for the epic bead that agent created instead.
- The goal of this feature is to allow users to launch sase agents earlier than they can
  now in some cases. Sometimes, for example, I need to wait for an agent to create an
  epic before I can launch a prompt (so I can pass that epic bead ID to the `%wait`
  directive's `bead` input). This feature makes it so I do not need to do that anymore.
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

# Research Report Summary: Dynamic Epic Waiting in `%wait` (`for_epic`)

**Researcher:** `research.3v.gem`  
**Report File:** [`wait_directive_for_epic_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/wait_directive_for_epic_design__gem.md)  
**Registered Artifact:** `file:explicit:e22a62a27753c03c3a404b21` (`research:202610/wait_directive_for_epic_design__gem.md`)

---

## Executive Summary & Core Verdict

The proposal to allow a downstream agent to dynamically wait for the epic bead created by a progenitor agent via `%wait(..., for_epic=true)` addresses a genuine operational friction in SASE. Today, multi-stage pipelines cannot be launched ahead of time because downstream agents must wait for an epic bead ID that does not yet exist.

### Core Critique & High-Level Adjustments
1. **The Proposed Default (`default=true`) MUST Be Rejected:**
   - *Issue:* Defaulting to `for_epic=true` whenever an agent name is passed to `%wait` silently breaks existing workflows. Specifically, plan-review agents, telemetry bots, and notification handlers that depend on the planning agent's turn completion would be stalled for days or weeks waiting for the entire multi-phase epic to finish before reviewing the plan to start it.
   - *Adjustment:* `for_epic` **must remain strictly opt-in** (`default=false`). Downstream prompts explicitly opt in via `%wait(planner, for_epic=true)` or flag shorthand `%wait(planner, for_epic)`.
2. **The Asynchronous Gate Gap (Critical Race Condition):**
   - *Issue:* When an epic planner finishes execution, the epic bead **does not exist yet**; it exists only as a proposed plan awaiting human or auto-approval in a `PlanGate`. If the wait resolution engine evaluates the planner immediately upon process termination and sees no epic bead, it would erroneously conclude "no epic was created" and unblock prematurely.
   - *Adjustment:* The resolution engine must recognize that while the plan gate is pending (`outcome == "gated"`), the progenitor agent is not yet resolved. It transitions to the epic bead only once the gate is approved (`outcome == "epic_approved"`).
3. **Artifact / Bead Linking Reality Check:**
   - *Finding:* SQLite attribution (`Issue.created_by`) exists and accurately records the creator/proposer agent name. However, SASE's formal *artifact link projection graph* (`src/sase/artifact_links/projection/`) does not currently project `agent:<name> produced bead:<id>`.
   - *Adjustment:* Add a new projection rule (`agent-created-bead`) to formally link `produced` / `produced-by` edges in the durable link graph.

---

## Architecture & System Design

### 1. Macro & Directive Layer (`src/sase/macro/`)
- Extend `supported_keys` in [`_directive_collect.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/macro/_directive_collect.py) to admit `for_epic`.
- Update [`PromptDirectives`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/macro/_directive_types.py) to track `wait_for_epic: dict[str, bool]`.
- Add diagnostic validation: using `for_epic` without an agent target (e.g. `%wait(bead=xyz, for_epic=true)`) raises an immediate, helpful `DirectiveError`.

### 2. Two-Stage Wait Resolution State Machine
Building directly on SASE's existing multi-stage wait precedent in [`run_agent_wait.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/axe/run_agent_wait.py) (which transitions dependency waits into post-dependency duration waits):
1. **Stage 1 (Agent Wait):** Parked runner writes `waiting.json` with `waiting_for: ["planner"]` and `wait_for_epic: {"planner": true}`.
2. **Stage 1.5 (Gate Hold):** If `planner` is gated awaiting plan review, the runner remains waiting.
3. **Transition Point (Dynamic Handoff):** Once `planner` resolves with `"epic_approved"`, the resolution engine queries the bead store for `created_by == "planner" AND tier == "epic"`.
4. **Stage 2 (Epic Wait):**
   - The runner rewrites `waiting.json`: swaps `waiting_for: []` for `wait_for_beads: ["sase-100"]` and records provenance `wait_for_epic_handoff: {"sase-100": "planner"}`.
   - `wait_checks` ([`_chop_wait_checks_run.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/scripts/_chop_wait_checks_run.py)) monitors `sase-100` until it is closed, then writes `ready.json`.

---

## TUI Experience: Intuitive, Reliable, Beautiful

### 1. Agent List Status Column ([`_agent_list_render_agent_status.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/ace/tui/widgets/_agent_list_render_agent_status.py))
- **Stage 1 (Waiting for Agent to Produce Epic):**
  ```text
  WAITING  planner ➔ [epic]
  ```
  *(Amethyst `#AF87FF` status badge, violet agent tag, dim cyan `[epic]` target glyph).*
- **Stage 2 (Handoff Complete — Waiting for Epic Bead):**
  ```text
  WAITING  sase-100 ‹ planner
  ```
  *(Primary wait target shifts to `sase-100` with active bead status color, while retaining dim provenance `‹ planner` so the user immediately understands why the agent is waiting on `sase-100`).*

### 2. Prompt Detail Panel ([`_agent_wait_section.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/ace/tui/widgets/prompt_panel/_agent_wait_section.py))
Renders structured provenance lanes:
```text
╭─ Wait Dependencies ────────────────────────────────────────────────────────╮
│ Agents:  planner   [DONE]  ✓ epic produced                                  │
│ Epic:    sase-100  [IN PROGRESS]  (handed off from planner at 16:50)        │
│          ├─ Phases: 3 total · 1 active · 2 pending                          │
│          └─ Model:  claude-sonnet-4-6                                       │
╰─────────────────────────────────────────────────────────────────────────────╯
```

### 3. Active TUI Toasts
When the dynamic handoff occurs while the user is in the TUI:
```text
ℹ Handoff: downstream-agent is now waiting for epic sase-100 (created by planner)
```

---

## Implementation Roadmap

1. **Phase 1: Macro & Directive Support:** Implement `for_epic` in `_directive_collect.py`, `_directive_extract.py`, and `PromptDirectives`; add syntax tests.
2. **Phase 2: Bead Store Query & Link Projection:** Implement `find_epic_beads_for_agent` in `store_locator.py` and register the `agent-created-bead` (`produced`/`produced-by`) projection rule in `_agent_bead.py`.
3. **Phase 3: Two-Stage Wait Engine:** Extend `run_agent_wait.py` and `_chop_wait_checks_run.py` to handle the dynamic transition from agent wait to epic bead wait.
4. **Phase 4: TUI Polish:** Add the `sase-100 ‹ planner` status rendering, `WaitLane` provenance display, and toast events.

---

## Deliverables & Registration
- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/wait_directive_for_epic_design__gem.md`
- **Durable Artifact Registration:**
  ```bash
  sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/wait_directive_for_epic_design__gem.md" -l "research:202610/wait_directive_for_epic_design__gem.md"
  # Registered: file:explicit:e22a62a27753c03c3a404b21
  ```
- **Final Declaration:** Submitted and accepted for the research report commit.
