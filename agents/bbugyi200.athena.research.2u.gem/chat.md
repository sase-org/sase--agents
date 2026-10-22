# Chat History - ace-run (research.2u.gem)

- **TIMESTAMP:** 2026-09-27 17:48:21 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2u.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_173702.md`

## Prompt

%id(gem, clan=research.2u)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2u.cdx`, `research.2u.cld`, `research.2u.grk`, `research.2u.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure what memory file
updates (if any) I should make once all sase goal epics are complete (none have been
planned yet). See the sase_goals_epic_roadmap.md file in the research sidecar repo for
context. Can you do some research with the goal of helping me decide? End your analysis
with a recommended set of memory file updates and/or additions you think I should
consider making. 
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

# Independent Research Report: SASE Goals Post-Completion Memory Strategy

**Researcher**: `research.2u.gem` (`__gem`)  
**Artifact Ref**: `file:explicit:715afeb1a50b54dc16ce1861`  
**Artifact Label**: `research:202609/sase_goals_memory_updates__gem.md`  
**Report Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/repos/research/202609/sase_goals_memory_updates__gem.md`

---

## Executive Summary & Core Conclusion

When all six SASE Goal epics (G1–G6) complete, SASE will have transitioned from an uncoordinated execution model driven by noisy, turn-by-turn completion pings into a structured, intent-driven architecture governed by the foundational invariant: **"The host binds, agents claim, users settle."**

Leaving memory unadjusted after G6 would create severe context drift: agents would remain unaware of the `%goal` directive, draft naming/adoption duties, finalizer claim obligations (`builtin@goal`), or the prohibition against invoking human status verbs. Conversely, inlining too much detail into Core Memory would bloat the prompt on every turn, violating SASE’s token-efficiency principles.

### Key Strategy Matrix

| Memory Tier / Target | Action | Purpose & Scope |
| :--- | :--- | :--- |
| **New Reference Note**<br>[`sase/memory/sase_goals.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/sase_goals.md) | **Create** | The comprehensive reference guide covering the Goal lifecycle (`draft` → `active` → `review` → `done`), binding rules, agent draft intake via `/sase_goal`, finalizer obligations (`builtin@goal`), evidence rules, and human-only status verb refusal. |
| **Core Memory**<br>[`sase/memory/sase.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/sase.md) (§1.1.4) | **Update (Minimal)** | Append a single sentence to the `/sase_final` terminal action contract stating that the final declaration records the turn's goal action (`keep_open` or `claim`). (~20 tokens). |
| **Reference Note**<br>[`sase/memory/sase_artifacts.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/sase_artifacts.md) | **Update** | Register `goal:` as a first-class canonical artifact kind (`goal:<id>`). Add the four new projection-sourced typed relations to the closed registry: `pursues`, `defines`, `evidences`, and `follows`. |
| **Reference Note**<br>[`sase/memory/xprompts.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/xprompts.md) | **Update** | Add `%goal:<id>` and `%goal:new` launch directives and generalized inheritance. Document `builtin@goal` as a required finalizer ordered after `commit`, and detail the final manifest goal payload. |
| **Reference Note**<br>[`sase/memory/sase_beads.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/sase_beads.md) | **Update** | Formalize the separation of concerns: Beads track work items (plans, phases, tasks); Goals track intent and verification. Clarify phase worker `keep_open` vs land agent `claim`. Note that status verbs on both beads and goals are refused inside agent runs. |
| **Reference Note**<br>[`sase/memory/generated_skills.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/generated_skills.md) | **Update** | Document the `/sase_goal` skill (`list`, `show`, `name`, `adopt`). Explicitly document that there is **no** `/sase_new_goal` skill. Note the `/sase_final` manifest expansion. |
| **Reference Note**<br>[`sase/memory/cli_rules.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/cli_rules.md) | **Update** | Codify the system-wide safety invariant: commands with human-only status mutation verbs (`verify`, `reject`, `drop`, `merge`, `reopen`) must refuse execution when run inside agent environments. |
| **Reference Notes**<br>[`sase/memory/tui.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/tui.md) & [`tui_perf.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_51/sase/memory/tui_perf.md) | **Update** | Document the top-level `Goals` tab in `TAB_ORDER`, its keybindings (`v`, `r`, `x`, `l`, `e`, `m`, etc.), and strict performance budgets (projection refresh < 2 ms at $n=100$, highlight → paint $\le 16\text{ ms}$). |
| **Decision Web** (`decisions`) | **Add 3 Strands** | 1. `goals-host-binds-agents-claim-users-settle`<br>2. `goal-ledger-cohosted-in-beads`<br>3. `attention-cutover-claim-based-notifications` |
| **Glossary Web** (`glossary`) | **Add 8 Strands** | Add `goal`, `goal-claim`, `goal-draft`, `goal-verify-gate`, `goal-adoption`, `goal-ledger`, `answer-acknowledgement`, `idle-goal`. Update `artifact`, `gate-turn`, and `agent-turn`. |
| **Files Unchanged** | **No Change** | `sase_flags.md` (all beta scaffolding flags are removed by G6), `rust_core_backend_boundary.md` (architecture preserved), `task_types.md` (goals are not task beads), `lint_and_test.md`, `gotchas.md`. |

---

## Detailed Breakdown of Recommended Changes

### 1. New Reference Note: `sase/memory/sase_goals.md`

Create a new reference note under `sase/memory/sase_goals.md` parented to `AGENTS.md`.

```yaml
---
type: reference
parent: AGENTS.md
description: Read before creating, binding, claiming, adopting, or verifying SASE goals — goal lifecycle, draft naming and adoption rules, finalizer claim obligations, and human-only status verbs.
---
```

#### Content Outline:
1. **Core Model & Invariant**: Explains *"The host binds, agents claim, users settle"*, the distinction between beads (work units) and goals (intent/verification), and the goal lifecycle (`draft` → `active` → `review` → `done · acknowledged` / `done · verified` / `dropped`).
2. **Host Binding & Directives**: Documents pre-execution resolution via `build_agent_meta`, `%goal:<id>`, `%goal:new`, refusal to bind settled goals, and generalized inheritance across children, retries, monitors, and dispatches.
3. **Drafts, Naming, and Adoption**: Documents machine-local draft assignment for uncoordinated turns, intake block handling, draft naming and active goal adoption via `/sase_goal`, prompt publication triggers, and the swarm single-goal invariant.
4. **Finalizer Obligations (`builtin@goal`)**: Documents the required finalizer ordered after `commit`, the phase vs land agent claiming restriction (phase workers only choose `keep_open`; land agents/single workers can `claim`), claim payload requirements (1–3 check-it steps, resolvable evidence refs, gaps), and fail-open resilience.
5. **Settling & Verification**: Documents `GoalVerify` gates, human verification workflows, automatic answer acknowledgement on open, and the strict refusal of human status verbs (`verify`, `reject`, `drop`, `reopen`, `merge`) inside agent runs.
6. **CLI & Skill Interface**: Details `sase goal` subcommands and the `/sase_goal` skill contract.

---

### 2. Core Memory Addition: `sase/memory/sase.md`

`sase.md` is inlined into all provider instruction shims on every turn. To avoid context bloat, append only a single compact clarification to §1.1.4 (**SASE Final Declaration**):

> *"That declaration commits your modified repositories and records your goal action (`keep_open` with progress note, or `claim` with verification evidence)."*

**Token Impact**: ~20 tokens added to core memory.

---

### 3. Updates to Existing Reference Memory Notes

- **`sase/memory/sase_artifacts.md`**:
  - Add `goal:` as a first-class canonical artifact kind (`goal:<id>`) rendered via `sase artifact read goal:<id>`.
  - Add `@goal:<id>` as prompt citation syntax.
  - Register four new projection-sourced typed relations in the closed registry:
    - `pursues` (inverse `pursued-by`, agent → goal)
    - `defines` (inverse `defined-by`, plan → goal)
    - `evidences` (inverse `evidenced-by`, commit/receipt/artifact → goal)
    - `follows` (inverse `followed-by`, goal → goal)
- **`sase/memory/xprompts.md`**:
  - Add `%goal:<id>` and `%goal:new` to the directives table.
  - Document directive inheritance across child prompts, retries, session successors, and dispatches.
  - Document `builtin@goal` finalizer requirements and `/sase_final` goal manifest payloads.
- **`sase/memory/sase_beads.md`**:
  - Document the boundary: Beads track work items; Goals track intent and verification.
  - Clarify that approving an epic plan bead defines a goal (`defines`), phase beads pursue it (`pursues`), phase workers declare `keep_open`, and land agents submit `claim`. Closing an epic bead does not settle the goal.
  - Highlight the symmetrical status verb restriction: agents cannot hand-edit bead statuses, and agents cannot run `sase goal verify|reject|drop|reopen|merge`.
- **`sase/memory/generated_skills.md`**:
  - Document the generated `/sase_goal` skill (`list`, `show`, `name`, `adopt`).
  - Explicitly document that there is **no** `/sase_new_goal` skill.
- **`sase/memory/cli_rules.md`**:
  - Add the rule: commands with human-only status mutation verbs (`verify`, `reject`, `drop`, `merge`, `reopen`) must refuse execution when run inside agent environments.
- **`sase/memory/tui.md` & `tui_perf.md`**:
  - Document the top-level `Goals` tab in `TAB_ORDER` and its keybindings.
  - Document performance contracts: projection refresh < 2 ms at $n=100$; highlight → paint $\le 16\text{ ms}$.

---

### 4. Memory Webs: New Decision & Glossary Strands

#### Decision Web (`decisions/`):
1. **`goals-host-binds-agents-claim-users-settle.md`**: Foundational architectural decision establishing host binding, draft intake, finalizer claiming, and human/ack settlement. *(First move before G1 planning)*.
2. **`goal-ledger-cohosted-in-beads.md`**: Establishes immutable event sourcing + `live/` markers co-hosted in the beads repository via hidden-clone writes and fast-path local projections.
3. **`attention-cutover-claim-based-notifications.md`**: Establishes the silencing of raw agent completion pings in favor of claim gates, decisions, and error alerts.

#### Glossary Web (`glossary/`):
- **New Strands**: `goal`, `goal-claim`, `goal-draft`, `goal-verify-gate`, `goal-adoption`, `goal-ledger`, `answer-acknowledgement`, `idle-goal`.
- **Updated Strands**: `artifact` (include `goal:`), `gate-turn` (include `GoalVerify`), `agent-turn` (bound goal and finalizer obligation).

---

### 5. Files Evaluated and Deliberately Kept Unchanged

- **`sase_flags.md`**: Unchanged. All temporary beta scaffolding flags introduced across G1–G5 are deleted by G6 before program close. No permanent flags remain.
- **`rust_core_backend_boundary.md`**: Unchanged. Goals strictly adheres to this boundary (`sase-core` owns wire types, ledger, reducer, and fast paths; Python owns TUI and launch glue).
- **`task_types.md`**: Unchanged. Goals are not task beads; task types remain `bug`, `ci`, `feature`, `flake`, `memory`.
- **`lint_and_test.md` & `symvision.md`**: Unchanged. Standard verification contracts apply equally to Goals code.

---

## Token Budget Impact

- **Always-Loaded Core Increase**: ~20 tokens in `sase.md`.
- **Always-Loaded Reference & Web Catalogs in `AGENTS.md`**: ~60 tokens (catalog line entries).
- **Net Always-Loaded Footprint**: **~80 tokens total** (< 1.5% increase in base instruction overhead).
- **On-Demand Context**: ~4,500 tokens across `sase_goals.md`, updated reference notes, and web strands, loaded **only** when an agent audits reads in those specific domains.

---

## Action Plan & Phased Rollout

1. **Pre-G1**: Land decision strand `goals-host-binds-agents-claim-users-settle` in `sase/memory/decisions/` so all six epic plans cite it.
2. **G1–G2**: Add `goal:` kind and `pursues`/`defines` relations to `sase_artifacts.md`; update `cli_rules.md`; add `goal` and `goal-ledger` to glossary.
3. **G3–G4**: Update `xprompts.md`, `sase_beads.md`, and `generated_skills.md`; add `goal-claim`, `goal-draft`, `goal-verify-gate`, `goal-adoption`, and `answer-acknowledgement` to glossary.
4. **G5**: Update `tui.md` and `tui_perf.md`.
5. **G6 Cutover**: Write `sase_goals.md`; update §1.1.4 in `sase.md`; land remaining decision strands; run `sase memory init` to regenerate `AGENTS.md` and provider shims; verify zero drift with `sase memory init --check`.

---

_The complete investigation report has been committed and registered as an explicit artifact: `research:202609/sase_goals_memory_updates__gem.md` (`file:explicit:715afeb1a50b54dc16ce1861`)._
