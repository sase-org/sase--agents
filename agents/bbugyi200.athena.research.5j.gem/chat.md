# Chat History - ace-run (research.5j.gem)

- **TIMESTAMP:** 2026-10-30 16:22:55 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5j.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261030_155916.md`

## Prompt

%id(gem, clan=research.5j)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5j.cdx`, `research.5j.cld`, `research.5j.grk`, `research.5j.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Why did the `16h.f0` sase agent start before the `16h` sase agent finished its work? The
`16h.f0` sase agent had `fork:16h` in its prompt so I was expecting it to wait for the
`16h` sase agent to complete before starting. With that said, since we have the ability
to specify that coder agents wait for another agent (in the coder options for a tale's
gate in the TUI, for example), it would be useful to be able to specifify whether an
agent should target the agent session or the currently running turn for that agent (this
seems to be what the `16h.f0` sase agent targeted).

- We could implement this with a new `target=<target>` input on the `fork` macro.
- The `<target>` input value would be required to be either "session" or "turn" (with a
  default of "session"). We should enforce this using an enum macro input type (this is
  the same type we use for inputs that accept model names I believe).

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

# Independent Research Report: Analysis of `#fork` and `%wait` Session vs. Turn Target Synchronization

**Researcher:** `gem` (5-Researcher Swarm)  
**Report Artifact:** `research:202610/fork_target_session_vs_turn_wait__gem.md`  
**Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202610/fork_target_session_vs_turn_wait__gem.md`  
**Artifact Ref:** `file:explicit:879fc169910d6149413794fa`

---

### 1. Why Did Agent `16h.f0` Start Before `16h` Finished Its Work?

Forensic analysis of the durable artifacts across `gh_bobs-org__bob-cli` reveals the exact microsecond chain of events:

1. **Launch State at 15:22:37 EDT**:
   When `16h.f0--plan` was launched with `#fork:16h` in its prompt, agent session `16h` was actively running its first turn: `16h--plan` (`20261030151600`).
2. **Turn-Level Binding in `fork_wait_dependency`**:
   `#fork:16h` generated an implicit wait dependency via `fork_wait_dependency("16h")` (`src/sase/agent/fork_waits.py`). Because `16h` was currently in its first turn and had not yet attached a successor (its gate turn), `find_agent_session("16h")` fell back to `find_named_agent("16h")`. This bound `wait_for_fork_sources` to **`kind: "agent"`** pointing explicitly to artifact `20261030151600` (`16h--plan`), rather than to the session container `kind: "session"`.
3. **Turn Completion vs. Session Settlement**:
   At 15:25:08.573959 EDT, `16h--plan` finished its execution and recorded `done.json` with `"outcome": "completed"` and `"finished_at": 1793388308.573959`.
4. **Immediate Wait Release**:
   The `wait_checks` lumberjack chop evaluated `dependency_resolution_status`. Because `16h.f0` was bound to the single turn `16h--plan`, the chop saw that `16h--plan` had reached a terminal state. It recorded `wait_dependencies_satisfied_at: 1793388308.573959` and wrote `ready.json`, releasing `16h.f0--plan` at **15:25:39 EDT**.
5. **Concurrent Execution**:
   `16h.f0--plan` booted and began running its LLM turn at **15:27:18 EDT**. Meanwhile, `16h` was still in the middle of its lifecycle: its plan gate (`16h--gate`) was created at 15:25:01 and answered at 15:29:53, and its coder turn (`16h--code`) ran from 15:30:48 until 15:51:26 EDT!
6. **Underlying Core Bug in Gate Handoff Tracking**:
   Even if `16h` had been bound as `kind: "session"`, `turn_followup_handoff_agent` in `src/sase/core/wait_dependency_resolution/_artifact_state.py` only inspects `monitor` and `gate` turns. When an agent turn (`16h--plan`) finishes with a gate handoff, it records `"outcome": "completed"`. Because `turn_followup_handoff_agent` returns `None` for agent turns, `_index_entities.py` treats `handoffs_present` as `True` and evaluates `is_done = any(candidate.is_done for candidate in effective_generation)`. Because `16h--plan` was done, the session engine declared the entire session "done" prematurely.

*(Note: `16h.f0--code` later waited properly because when `16h.f0--gate` was approved, the reviewer entered `wait_agents: ["16h"]`, generating `%wait(16h)`. At that time, `16h--code` was actively executing, so `%wait(16h)` waited on `16h--code` and unblocked when it finished at 15:51:26).*

---

### 2. Critique of the Proposed Plan (`target=<target>` on `fork` Macro)

The proposed plan suggests adding a `target=session|turn` input to the `fork` macro with enum validation (defaulting to `"session"`). While the intuition is understandable, **this mechanism cannot work as conceived**:

1. **Timing Mismatch: `#fork` is Launch-Deferred**:
   `#fork` is defined in `LAUNCH_DEFERRED_MACRO_NAMES` (`src/sase/macro/processor.py`). Macro expansion and step execution in `src/sase/macros/fork.yml` occur **only after** an agent has crossed its wait barrier and been admitted. When the agent is waiting in AXE, `fork.yml` has not run yet. Adding inputs to `fork.yml` has zero effect on the pre-wait dependency loop.
2. **Macro Grammar Constraint: `validate_repeatable_input_order`**:
   In `src/sase/macros/fork.yml`, `name` has `repeatable: true`. SASE enforces that a repeatable input must be the final user-facing positional input.
   - If `target` is added after `name`, `validate_repeatable_input_order` rejects the macro with `MacroValidationError`.
   - If `target` is added before `name`, it becomes positional argument 0. Any standard call like `#fork:16h` will pass `"16h"` to `target`, breaking every existing `#fork:<name>` in SASE.
   - SASE macro input declarations currently do not support keyword-only flags.
3. **Lexical Regex Discards Keyword Arguments**:
   The pre-wait reference extractor (`_resume_reference_arguments` in `src/sase/agent/names/_resume.py`) parses the argument string with `parse_args` and explicitly ignores named arguments: `positional, _ = parse_args(...)`. A call like `#fork(16h, target=session)` discards `target=session`.
4. **Input Type Clarification**:
   Model inputs do *not* use `type: enum`. They use `named_type: "model"` with dynamic Rust validation (`classify_model_value`). Macro enums use `type: enum` with a static `choices:` list (as in `src/sase/macros/pr.yml`).
5. **Scope Mismatch with TUI Coder Options**:
   When approving a tale's gate in the TUI, the coder options generate **`%wait(16h)`**, not `#fork`. Putting `target=` only on `#fork` leaves TUI coder options unable to benefit from session-vs-turn control.

---

### 3. Recommended Solution

A clean, robust solution requires addressing the problem across three distinct layers:

#### Layer 1: Fix Core Session Lifecycle Tracking (Bug Repair)
- **Session Identity Preservation**: In `fork_wait_dependency` (`src/sase/agent/fork_waits.py`), when a target matches a running agent whose session name is `name`, bind it as `kind: "session"` from the start, rather than falling back to `kind: "agent"`.
- **Handoff Tracking on Agent Turns**: In `src/sase/core/wait_dependency_resolution/_artifact_state.py`, update `turn_followup_handoff_agent` to recognize agent turns that hand off to gates (`gate_member_agent_name` or `gate_id`), registering a pending follow-up agent.
- **Session Settlement Requirement**: In `_index_entities.py`, update session `is_done` so it is not satisfied by `any(is_done)` when pending handoffs or active successors remain. A session wait should stay parked until the entire session chain has settled.

#### Layer 2: First-Class `%wait` Directive and TUI Support
- **Keyword Argument on `%wait`**: Extend `%wait` to accept `target=session|turn`:
  - `%wait(16h, target=session)` (default): Waits for the entire session chain to settle.
  - `%wait(16h, target=turn)`: Waits only for the currently active turn of `16h` to reach a terminal state.
- **Explicit Turn Suffix Support**: Honor SASE's canonical naming convention where bare names (`16h`) target sessions and suffixed names (`16h--plan`, `16h--code`) target individual turns. `%wait(16h--plan)` naturally waits only for that turn.
- **TUI Gate Coder Modal**: Update `sase.wait_spec` and `_WaitSpecInputModal` in the TUI to allow selecting "Session" vs. "Turn" when specifying coder agent wait dependencies.

#### Layer 3: Align `#fork` Context Injection and Argument Parsing
- **Update Reference Extractor**: Modify `_resume_reference_arguments` (`src/sase/agent/names/_resume.py`) to retain keyword arguments (`positional, named = parse_args(...)`).
- **Pass Target to Pre-Wait Flow**: When `#fork(16h, target=turn)` is used, propagate `target="turn"` to `fork_wait_dependency`.
- **Align Transcript Scoping**: In `src/sase/scripts/_agent_chat_from_name_sources.py`, ensure that `target="turn"` restricts transcript injection to just the specified turn, whereas `target="session"` injects the complete multi-turn session history.

---

### 4. Artifact Registration Confirmation

The comprehensive research report, complete with forensic timestamps, code traces, and architectural Mermaid diagrams, has been written and registered:
- **Local File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202610/fork_target_session_vs_turn_wait__gem.md`
- **Artifact Label:** `research:202610/fork_target_session_vs_turn_wait__gem.md`
- **Artifact Ref:** `file:explicit:879fc169910d6149413794fa`
- **Final Declaration:** Submitted and accepted for repository `sdd:research` (`repo-7f832d23d762`).
