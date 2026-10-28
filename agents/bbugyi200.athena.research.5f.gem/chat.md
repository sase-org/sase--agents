# Chat History - ace-run (research.5f.gem)

- **TIMESTAMP:** 2026-10-28 18:37:41 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5f.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261028_181306.md`

## Prompt

%id(gem, clan=research.5f)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5f.cdx`, `research.5f.cld`, `research.5f.grk`, `research.5f.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think we made a mistake having sase gates (including and especially plans) and sase
monitors kill the agent that invoked them. I would like to start requiring that agents
use a finalizer for gates and monitors instead.

- I'm thinking that the best way to do this is probably to just use the existing commit
  finalizer.
- This means that, after this change, all agent turns should be required to submit a
  final declaration (agents that proposed plans or ran monitors used to be excempt). We
  will need to make sure that the commit finalizer knows that it is okay for agents that
  propose plans or run monitors do not specify that a commit should be made.
- The benefits of this change:
  - Using finalizers to perform an agent's final action seems more intuitive than what
    we were doing before.
  - On a more practical note, this will give agents the ability to commit file changes
    and propose plans in the same turn. See the `bob-cli-dw.land` and `sase-1ou.land`
    sase agents for some context on why this might be useful.

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

# Research Report: Retiring Agent Kill Handoffs in Favor of Host Finalizers

The independent research report has been written to [gate_monitor_finalizer_completion__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/gate_monitor_finalizer_completion__gem.md) and registered as a durable artifact snapshot (`research:202610/gate_monitor_finalizer_completion__gem.md`, ref `file:explicit:777470313c27e088974c0e9a`).

---

### Executive Summary & Critique

#### 1. Is Retiring the Mid-Turn Agent Kill Model a Good Idea?
**Yes, unequivocally.** The current architecture—where `sase plan propose`, `sase monitor start`, and `sase gate create` invoke `kill_agent_runner_group()` to terminate the provider process group with `SIGTERM`—is a structural flaw with severe consequences:
- **Silent Loss of Work (Workspace Stranding):** Because `SIGTERM` kills the turn before finalizers run, any file changes made during the turn (e.g., updating existing plan files to `status: done`, adjusting configurations/baselines, or fixing bugs) are left uncommitted. When a proposed plan launches a child epic in a fresh workspace, the uncommitted workspace is abandoned.
  - *Concrete evidence:* In epic `bob-cli-dw` (bead `bob-cli-e0`), five consecutive backlog batch lander agents lost their `status: done` edits because each ended with `sase plan propose`. Lander `bob-cli-dw.land` had to explicitly refuse to propose plan B7 so it could end normally with `/sase_final` to preserve its test fixes and nine plan edits.
  - *Concrete evidence:* In `sase-1ou.land`, the lander fixed store contention in `sase-core`, but proposing the child epic terminated the turn prematurely, truncating its reasoning and forcing synthetic chat generation.
- **Transcript Corruption:** Killing the agent subprocess abruptly mid-tool execution (exit code 143) destroys the agent's concluding thoughts, forcing the runner to synthesize artificial chat responses (`format_plan_as_response`).
- **Contradictory Contracts:** Agents are told host completion is universal (`decisions:host-owned-completion`), but are simultaneously burdened with an arbitrary set of "mechanical exemptions" for handoffs.

---

#### 2. Critique of "Just Using the Existing Commit Finalizer"
While your goal of ending turns through finalizers is right, **overloading `builtin@commit` to execute gates, plans, and monitors should not be done.**

- **Separation of Concerns:** `builtin@commit` is a pluggable VCS finalizer provider responsible for discovering repository dirt and running `sase stitch create`. It should not manage gate shell lifecycle, plan validation/review dispatch, or monitor supervisors.
- **Fixed-Point & Recovery Semantics:** SASE finalizers iterate to a fixed point. If a commit encounters an error (conflict, dirty protected paths, invalid commit message), the turn must enter declaration/conflict recovery. If a plan or monitor handoff had already triggered inside the commit finalizer, an orphaned gate or child epic would launch while the parent turn was failing.
- **Clean State Handling:** The commit finalizer *already* handles clean workspaces without requiring commit payloads (`submission_required: false` in `declaration_store.py:225` and `commit_execution.py:133`). However, if an agent *did* modify files before proposing a plan, those files **must** be committed. Allowing an agent with dirty files to skip committing on a plan proposal would re-introduce the exact workspace stranding bug observed in `bob-cli-e0`.

---

### Recommended Architecture: Staged Intent + Universal Finalizers + Post-Finalization Transition

Instead of cramming orchestration into `builtin@commit`, adopt a clean, three-phase completion flow:

```mermaid
flowchart TD
    subgraph Flow["Turn Completion Flow"]
        A["Agent runs `sase plan propose` / `sase monitor start`"] --> B["Tool validates & records data\nStages intent marker in artifacts_dir\nReturns 0 (NO SIGTERM)"]
        B --> C["Agent completes reasoning & updates plan status\nCalls `/sase_final`"]
        C --> D["Host controller executes `run_finalizers()`\n(`builtin@commit`)"]
        D --> E{"Are repos dirty?"}
        E -- "Yes" --> F["`builtin@commit` commits all dirty repos\nvia `sase stitch create`"]
        E -- "No" --> G["`builtin@commit` confirms clean state\n(no commit payload required)"]
        F --> H{"Finalizers passed?"}
        G --> H
        H -- "Yes" --> I{"Staged handoff present?"}
        H -- "No" --> J["Enter Finalizer Recovery\n(Handoff blocked)"]
        I -- "Plan" --> K["Host creates plan gate shell\nLaunches review / child epic"]
        I -- "Monitor" --> L["Host transfers lane to monitor supervisor"]
        I -- "Gate" --> M["Host transitions to gate shell"]
        I -- "None" --> N["Turn settles as completed"]
    end
```

1. **Staged Intent (No Kill):**
   - `sase plan propose`, `sase monitor start`, and `sase gate create` drop `kill_agent_runner_group()`.
   - They validate inputs, write their pending markers/records (`.sase_plan_pending`, etc.), and return exit code 0 to the calling agent.
2. **Universal Final Declaration:**
   - Every root SASE agent turn concludes by calling `/sase_final` (`sase final context` + `sase final submit`). Mechanical exemptions are completely eliminated.
   - If the workspace is clean, `submission_required` is false.
   - If files were changed (plan sidecar `status: done`, code bug fixes), the agent specifies commit decisions and they are committed cleanly.
3. **Host Finalizer Execution:**
   - `should_skip_finalizers()` no longer skips finalizers when a handoff marker is present.
   - `run_finalizers()` executes `builtin@commit`. All dirty repos are committed before any handoff occurs.
4. **Host Post-Finalization Transition:**
   - Once all finalizers settle and succeed, the host runner inspects the staged handoff marker and transitions to the gate shell, child epic launcher, or monitor supervisor.
   - The agent's genuine final response is saved in the chat history, retiring the synthetic response generator.

---

### Implementation Plan & Scope

1. **`src/sase/main/plan_propose_handler.py`**: Remove `kill_agent_runner_group(artifacts_dir)`. Output next-step guidance to conclude with `/sase_final`.
2. **`src/sase/monitor/handoff.py` & `src/sase/main/monitor/start.py`**: Remove `kill_agent_runner_group(artifacts_dir)`. Return 0.
3. **`src/sase/gate_turn/agent_handoff.py`**: Remove `kill_agent_runner_group(artifacts_dir)`. Return 0.
4. **`src/sase/finalizers/controller_context.py`**: Remove `has_pending_handoff(artifacts_dir)` from `should_skip_finalizers()`.
5. **`src/sase/axe/run_agent_exec.py`**: Move handoff marker handling (`handle_plan_marker`, `handle_monitor_marker`, `handle_gate_marker`) to execute immediately after `run_finalizers()` returns successfully on clean provider exits.
6. **Skills & Memory**:
   - Update `sase_final` SKILL.md to remove handoff exemptions.
   - Update `decisions:gates-never-block` and `decisions:host-owned-completion` to reflect that all turns finalize through the host controller before transition.
