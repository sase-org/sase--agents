# Chat History - ace-run (research.2f.gem)

- **TIMESTAMP:** 2026-09-24 09:05:12 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2f.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_085243.md`

## Prompt

%id(gem, clan=research.2f)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2f.cld`, `research.2f.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been renaming a lot of sase concepts
to use terms that are more standard across the AI / tech industry lately. For example, I
renamed "axe" to "scheduler", "lumberjacks" to "routines", "chops" to "jobs", "ace" to
"tui", and am now in the process of (see the sase-17m epic bead and the `0qi` sase agent
for context) renaming "agent families" to "agent sessions" and "sase shells" to "sase
turns".

Can you do some research with the goal of critiquing these renames and searching for any
other concepts that you think should be renamed? Make sure that you have strong
justification if you recommend a new rename. End your analysis with a brief critique of
the renames that have already been implemented or will be implemented soon and a list of
new recommended renames that you think I should perform (if any). 
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

# Independent Research Report: SASE Concept Renames & Industry Standardization

**Author:** Researcher `gem` (Independent Research Swarm)  
**Deliverable File:** [`sase_concept_renames_and_terminology_standardization__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/research/202609/sase_concept_renames_and_terminology_standardization__gem.md)  
**Artifact Registration Ref:** `file:explicit:8eca324a10f6f55497cef93b`  
**Label:** `research:202609/sase_concept_renames_and_terminology_standardization__gem.md`

---

## 1. Executive Summary & Overview

SASE historically developed an idiosyncratic vocabulary centered around multiple distinct metaphors:
- **Forestry / Woodcutting:** `axe` (scheduler), `lumberjacks` (scheduled loops), `chops` (scheduled jobs).
- **Kinship / Anthropology:** `agent family` (sequential agent session), `agent clan` (parallel agent group), `agent tribe` (cross-cutting tag/label), `agent hood` (dotted-prefix namespace), `agent neighbor` (co-namespaced agent).
- **Textiles / Sewing:** `patch` (unit of change), `stitch` (incremental commit/revision).
- **Arachnid / Biology:** `memory web` (keyed note collection), `memory strand` (individual topic note).
- **Unix Overloading:** `sase shell` (agent / gate / monitor turn), `sase pipe` (turn handoff to successor agent), `task` (durable OS process, colliding with task beads).

The recent campaign to transition SASE away from bespoke folklore toward established AI and tech industry standards is a massive upgrade in developer ergonomics, onboarding speed, and LLM prompt grounding.

---

## 2. Critique of Implemented and In-Progress Renames

### Implemented Renames

1. **`axe` → `scheduler`**
   - **Verdict:** Highly successful.
   - **Critique:** "AXE" was an opaque proper noun / forestry pun with zero operational intuition. "Scheduler" is universal across operating systems and distributed task frameworks (`cron`, APScheduler, Airflow). It immediately communicates process lifetime and periodic evaluation.

2. **`lumberjacks` → `routines`**
   - **Verdict:** Strong improvement, with minor technical nuance.
   - **Critique:** Retires the folksy lumberjack metaphor in favor of a recognizable English noun conveying recurring procedural maintenance ("scheduled routines"). While "routine" has slight historical overloading in CS (subroutines / functions) and SASE routines are full OS processes, within user-facing config (`sase.yml`) and the TUI ("Scheduled Routines"), it functions cleanly as a grouping of scheduled jobs.

3. **`chops` → `jobs`**
   - **Verdict:** Flawless.
   - **Critique:** "Job" is the universal industry standard for discrete, script-level automation units with cadence, timeouts, and execution logs (Unix cron jobs, Slurm jobs, CI jobs, Kubernetes Jobs). Completely removes personal repository jargon (`bugyi-chops`).

4. **`ace` → `tui`**
   - **Verdict:** Excellent and grounded.
   - **Critique:** Previously `sase ace` conflated the terminal interface with the broader autonomous runtime. Renaming the command and surface to `sase tui` aligns with standard developer tools (`lazygit`, `tig`, `gh dash`) and cleanly scopes the Textual presentation layer from backend orchestration.

### In-Progress Renames

5. **`agent families` → `agent sessions` (Epic `sase-17m`)**
   - **Verdict:** Outstanding architectural and cognitive alignment.
   - **Critique:** In plain English and CS, a "family" is an unordered set or collection of entities (family of curves, family of fonts, process family). This led users and models to wrongly assume an "agent family" was a parallel group or team of agents. In reality, a SASE family is a **strictly sequential chain** of agent executions sharing state and a workspace. Renaming this to **`agent session`** matches universal LLM and developer agent standards (Claude Code sessions, OpenAI Assistant threads/sessions, Cursor composer sessions, Aider chat sessions).

6. **`sase shells` → `sase turns` (Agent `0qi`)**
   - **Verdict:** Essential and overdue.
   - **Critique:** Calling an agent execution a "shell" was a catastrophic domain collision with Unix shells (`/bin/sh`, `/bin/bash`, interactive subshells, terminal windows). Furthermore, SASE's core architectural principle (Decision 3: `single-turn-agents`) literally states: *"A SASE agent run is one provider turn; continuation is always mechanical, never a promise to resume."* Renaming `agent shell` → `agent turn` and `gate shell` → `gate turn` harmonizes the codebase with conversational AI dialogue theory and SASE's own architectural contract.

---

## 3. Audit of Remaining Concepts & Recommendations for New Renames

A systematic audit reveals 5 major areas where residual metaphors, colloquialisms, or domain collisions still create friction.

### Area 1: The Broken Kinship Metaphor (`clan`, `tribe`, `hood`, `neighbor`)
Now that `agent family` is being renamed to `agent session`, the kinship metaphor has been dismantled. However, its satellite concepts remain stranded:

1. **`agent tribe` → Recommend: `agent tag` (or `agent label`)**
   - *Justification:* In SASE, a "tribe" is simply a user-facing label prefixed with `@` applied across agents (e.g. `@research`, `@frontend`). Crucially, SASE's codebase reveals that **this was previously called `agent tag`** (see `tests/test_agent_tribe_terminology.py`). It was renamed to "tribe" solely to fit with "family". With "family" gone, "tribe" has no thematic anchor. In tech, arbitrary cross-cutting user metadata is universally called a **tag** (Git tags, AWS tags) or **label** (Kubernetes labels, GitHub labels).
2. **`agent clan` → Recommend: `agent swarm` (or `agent team` / `agent pool`)**
   - *Justification:* SASE defines an "agent clan" as a named container for agents running in *parallel* toward a goal. In modern AI, parallel multi-agent executions are universally termed **swarms** (OpenAI Swarm) or **teams** (CrewAI, AutoGen). SASE already uses "swarm" everywhere (including `xprompt swarm` and researcher swarms). "Clan" has zero precedent in CS or AI.
3. **`agent hood` → Recommend: `agent namespace` (and `agent neighbor` → `peer agent`)**
   - *Justification:* SASE defines an "agent hood" as agents sharing a hierarchical dotted prefix (`foo.bar`, `foo.baz` are in the `foo` hood). In computing, hierarchical prefix grouping is universally called a **namespace**. "Hood" is jarringly informal slang.

### Area 2: The Unix Pipe Misnomer (`sase pipe` → `sase handoff`)
4. **`sase pipe` → Recommend: `sase handoff` (or `sase turn next`)**
   - *Justification:* In Unix, a `pipe` streams bytes between concurrent processes. In SASE, `sase pipe` does not stream bytes; it terminates the current agent turn and triggers the next agent turn in the session with a successor prompt. In modern multi-agent systems (OpenAI Swarm, LangGraph, CrewAI), this control delegation is universally termed a **handoff**. SASE's own internal implementation in `src/sase/main/pipe_handler.py` literally names its payload serializer `_pipe_handoff_json`!

### Area 3: The Sewing Metaphor in VCS (`stitch` → `revision` or `commit`)
5. **`stitch` → Recommend: `revision` or `commit`**
   - *Justification:* SASE uses a sewing metaphor: a `Patch` contains `Stitches`. In stacked-diff systems (Jujutsu `jj`, Graphite, Gerrit, Phabricator), each discrete unit in a patch is a **revision** or **commit**. SASE's own glossary strand acknowledges the confusion: *"The `sase stitch create` command and real Git/Mercurial commits are still called commits."* Aliasing `sase stitch` to `sase vcs` further reflects this dissonance. Renaming `stitch` to `revision` eliminates an artificial metaphor.

### Area 4: The Arachnid Memory Metaphor (`memory web` / `strand` → `collection` / `entry`)
6. **`memory web` / `memory strand` → Recommend: `memory collection` / `memory entry`**
   - *Justification:* SASE's own glossary definition immediately translates the metaphor into standard terms: *"A memory web is a keyed note collection... One note inside a Memory Web"*. In knowledge bases, RAG, and memory architectures (MemGPT/Letta, Zep, LangChain), grouped topic notes are **collections** or **categories**, and individual documents are **entries** or **documents**.

### Area 5: CLI Subcommand Collision (`sase proc (task)`)
7. **Deprecate the `task` alias on `sase proc`:**
   - *Justification:* In `sase --full-help`, `task` is an alias for `sase proc` (durable OS processes). Meanwhile, SASE's primary issue tracking primitive in `sase bead` is a `task` bead (`sase bead create -T "task(bug)"`, `sase bead ready`). Having `sase task` drop into OS process controls rather than task bead management creates a severe naming collision.

---

## 4. Prioritized Action Plan for Recommended Renames

| Priority | Proposed Rename | Replaces | Primary Justification |
| :--- | :--- | :--- | :--- |
| **Tier 1 (High ROI)** | **`agent tag`** (or `label`) | `agent tribe` | Restores pre-kinship standard term; matches universal `@` tagging conventions. |
| **Tier 1 (High ROI)** | **`sase handoff`** | `sase pipe` | Eliminates false Unix streaming expectations; matches multi-agent handoff standards and SASE's own internal code. |
| **Tier 1 (High ROI)** | **Deprecate `task` alias on `proc`** | `proc (task)` | Eliminates direct CLI collision with `task` beads. |
| **Tier 2 (Structural)** | **`agent namespace`** / **`peer agent`** | `agent hood` / `neighbor` | Replaces colloquial slang with standard CS terminology for dotted-prefix scoping (`foo.*`). |
| **Tier 2 (Structural)** | **`agent swarm`** (or `team`) | `agent clan` | Aligns parallel multi-agent grouping with established AI terminology and SASE's existing "swarm" usage. |
| **Tier 3 (Polish)** | **`memory collection`** / **`entry`** | `memory web` / `strand` | Normalizes knowledge base documentation taxonomy. |
| **Tier 3 (Polish)** | **`revision`** (or `commit`) | `stitch` | Aligns stacked-diff VCS workflow with Jujutsu/Graphite/Git standards. |

---

## 5. Artifact Verification

The full research report has been written and registered as a durable artifact snapshot:
- **File path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/research/202609/sase_concept_renames_and_terminology_standardization__gem.md`
- **Artifact Ref:** `file:explicit:8eca324a10f6f55497cef93b`
- **Artifact Label:** `research:202609/sase_concept_renames_and_terminology_standardization__gem.md`

The finalizer declaration for the `commit` instance has been successfully submitted and accepted:

- **Repository**: `repo-bf70b2778b7c` (`sdd:research`)
- **Action**: `commit`
- **Commit Message**: `docs(research): critique concept renames and recommend terminology standardization`
- **Status**: `Accepted final declaration for: commit`
