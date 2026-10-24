# Chat History - ace-run (research.58.gem)

- **TIMESTAMP:** 2026-10-24 18:00:24 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.58.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261024_174818.md`

## Prompt

%id(gem, clan=research.58)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.58.cdx`, `research.58.cld`, `research.58.grk`, `research.58.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to start setting sase variables automatically whenever the /sase_questions
skill is used. The goal of this change is to make it so when the user selects an agent
session on the "Agents" tab that is associated with an agent turn that asked questions,
those questions, their recomended answers, their actual answers (if any questions have
been answered yet), and how the questions were answered (if any questions have been
answered yet) are all immediately visible (since variables are rendered in the main
deck).

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

# Research Report: SASE Questions Deck Visibility & Output Variables

**Researcher:** `research.58.gem` (Swarm Member `gem`)  
**Report Artifact:** [`sase_questions_output_variables_and_deck_visibility__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/sase_questions_output_variables_and_deck_visibility__gem.md)  
**Registered Artifact Reference:** `file:explicit:89c4f91a01ffad5448da9786` (`research:202610/sase_questions_output_variables_and_deck_visibility__gem.md`)

---

## Executive Summary & Critique

The goal of making question state immediately visible in the TUI main deck when an operator selects an agent session on the "Agents" tab—showing the questions asked, recommended choices, actual answers, and answer provenance—addresses a genuine UX blind spot. Today, sessions in `QUESTION` status require opening modals or inspecting raw JSON gate logs to determine what was asked.

However, **setting SASE output variables (`sase var`) automatically as the transport mechanism to achieve this visibility is an architectural antipattern.**

### Why Using `sase var` is Problematic
1. **Domain & Semantic Conflation:** Output variables are designed for *agent-produced computational facts* (e.g., artifact paths, build status flags, `STOP`). Questions and answers are an *interactive negotiation with a human or policy*. An answer provided by a user is an external input into a subsequent turn, not an output variable of the asking agent.
2. **Lifecycle Asymmetry & Turn Immutability:** When `/sase_questions` runs, the agent process group is killed via `SIGTERM` within ~100ms. At ask-time, the actual answers and resolution provenance do not exist. Setting them later requires either retroactively mutating the dead agent's `agent_meta.json` (violating turn finality) or writing to the gate turn's metadata, which creates awkward role attribution in the UI (`gate: questions: ...`).
3. **Downstream Context Window Pollution:** Variables are automatically exposed to downstream turns in Jinja templates via `{{ agents["name"].key }}`. Storing verbose question schemas, option descriptions, and user feedback in `output_variables` inflates prompt token overhead for all subsequent agents in the workflow.
4. **Enforced Resource Limits:** SASE enforces strict caps on output variables (`sase.core.output_variable_values`): max 8 KiB per leaf string, max 65,536 bytes encoded JSON, and max 1,024 AST nodes. Detailed multi-question rounds or lengthy reviewer notes risk hitting these caps.
5. **Suboptimal UI Presentation:** `_output_variable_rich.py` renders variables using flat, generic YAML key-value lines. It cannot render interactive checkboxes (`[x]`), status badges (`[RECOMMENDED]`, `[Answered via TUI]`), or formatted markdown blocks.
6. **Redundant State Duplication:** SASE **already canonically stores** every question, option, answer, reviewer note, caller identity (`human`/`agent`), and resolution surface (`"tui"`, `"telegram"`, `"mobile"`, `"auto"`, `"cli"`) in the gate bundle (`request.json` and `response.json`). Setting variables merely creates a second, denormalized copy prone to sync bugs on timeouts or cancellations.

---

## The Recommended Approach: First-Class Questions Deck Section

Rather than using output variables as a proxy to force text into the UI, SASE should implement a **dedicated Questions & Answers Section in the Main Deck**:

- **Location:** Integrated either into the Prompt Panel context card (`src/sase/ace/tui/widgets/prompt_panel/_agent_display_header.py`) or as a specialized phase in the Gate Turn reply block (`src/sase/ace/tui/widgets/prompt_panel/_agent_gate_section.py`).
- **Data Source:** Reads directly from canonical gate files (`request.json` and `response.json`) via existing loader helpers (`sase.question_gate_turn.rounds:question_rounds()`).
- **Zero Invalidation / Duplication:** Reads the source of truth directly; no secondary variables to keep in sync.
- **Immediate Retroactive Support:** Instantly illuminates **every historical question session in SASE history** without data migration scripts.
- **Rich Visual Styling:** Native Textual/Rich rendering:
  ```
  ────────────────────────────────────────────────────────────────────────
  QUESTIONS & ANSWERS · Round 1 [ANSWERED via TUI modal]
  ────────────────────────────────────────────────────────────────────────
  Q1: Database Engine Selection
    > Which database engine should we adopt for the new storage tier?

    [x] PostgreSQL — Relational, mature, robust JSONB support [RECOMMENDED]
    [ ] SQLite — Embedded, zero-configuration
    [ ] Other

    Reviewer Note: "Approved for PG 16+. Do not use SQLite for this tier."
    Answered by: human via TUI modal · 2026-10-24 18:02:15 EDT
  ────────────────────────────────────────────────────────────────────────
  ```
  And when still pending:
  ```
  ────────────────────────────────────────────────────────────────────────
  QUESTIONS & ANSWERS · Round 1 [PENDING USER INPUT · 12m left]
  ────────────────────────────────────────────────────────────────────────
  Q1: Database Engine Selection
    > Which database engine should we adopt for the new storage tier?

    [ ] PostgreSQL — Relational, mature, robust JSONB support [RECOMMENDED]
    [ ] SQLite — Embedded, zero-configuration
    [ ] Other
  ────────────────────────────────────────────────────────────────────────
  ```

---

## Fallback Blueprint: If `sase var` Must Be Implemented

If programmatic access via `sase var get questions` is explicitly required for downstream scripting, implement the following schema and lifecycle hooks:

### 1. Unified Variable Schema
Store under a single reserved key `questions` (never N individual keys):
```json
{
  "questions": [
    {
      "index": 1,
      "header": "Database Engine",
      "question": "Which database engine should we adopt?",
      "recommended": "PostgreSQL",
      "multi_select": false,
      "status": "answered",
      "actual": ["PostgreSQL"],
      "custom_feedback": null,
      "source": "tui",
      "answered_by": "human",
      "answered_at": "2026-10-24T18:02:15Z"
    }
  ]
}
```

### 2. Mutation Lifecycle
- **At Ask-Time:** In `src/sase/question_gate_turn/create.py:create_question_gate_turn()`, initialize `output_variables` on the **Question Gate Turn Member** (`creation.record.artifacts_dir`) with `status: "pending"`, `recommended: options[0]["label"]`, `actual: null`. *(Setting it on the gate turn avoids mutating the dead asking agent, and `_output_variable_contributors` in the TUI already aggregates gate turn variables under `(agent, *agent.followup_agents)`).*
- **At Settle-Time:** In `src/sase/user_question_actions.py:execute_user_question_response()`, update the gate turn's `output_variables` with `status: "answered"`, `actual`, `custom_feedback`, `source`, `answered_by`, and timestamp.
- **At Auto-Resolution (%auto):** In `src/sase/axe/run_agent_exec_questions.py:_continue_after_auto_answered_question()`, record `source: "auto"`, `answered_by: "agent"`.
- **At Timeout / Cancellation:** In `src/sase/gate_turn/settlement.py:settle_gate_turn()`, update `status` to `"timed_out"` or `"cancelled"`.

---

## Refinements to Requirements

1. **Decouple Goal from Mechanism:** The requirement should specify *"Display full Q&A status prominently in the main deck for question sessions"* rather than prescribing `sase var` as the backend storage.
2. **Formalize Recommended Option Semantics:** Explicitly codify `options[0]` as the recommended choice across both UI rendering and data models (matching `sase_questions/SKILL.md` guidance) and display a clear `[RECOMMENDED]` visual cue.
3. **Capture Dual Provenance:** Track both the **Resolution Surface** (`"tui"`, `"telegram"`, `"mobile"`, `"auto"`, `"cli"`) and the **Caller Identity** (`"human"` vs `"agent"`). Both are already captured in `response.json`.
4. **Handle Multi-Question & Multi-Round Sequences:** Ensure the deck presentation cleanly structures arrays of multiple questions within a round and stacks multiple chronological rounds (`Round 1`, `Round 2`).
