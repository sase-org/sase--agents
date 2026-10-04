# Chat History - ace-run (research.k.gem)

- **TIMESTAMP:** 2026-09-28 12:37:28 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.k.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_122749.md`

## Prompt

%id(gem, clan=research.k)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.k.cdx`, `research.k.cld`, `research.k.grk`, `research.k.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure about
our plans to implement "goals" for sase.

- See the sase_goals_epic_roadmap.md file in the research sidecar repo and the sase-1bu
  epic bead for context.
- In particular, if the only value-add is better notifications (so users are only
  notified when work they asked for is complete), couldn't we just customize xprompt
  swarms and/or agent clans to only send a completion notification for certain agents?

Can you do some research with the goal of critiquing this idea and helping me decide
whether I should press forward with this or not? End your analysis with a
recommendation. 
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

# Independent Research Report: SASE Goals Value Critique & Clan-Level Notification Silencing

**Researcher:** `research.k.gem`  
**Report File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/goals_value_and_notification_critique__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/goals_value_and_notification_critique__gem.md)  
**Registered Artifact Ref:** `file:explicit:85f938e0a8de02b1fd1f5fe7` (`research:202609/goals_value_and_notification_critique__gem.md`)

---

## 1. Executive Summary & Core Conclusion

You asked whether SASE should press forward with implementing **Goals** (a 6-epic, ~35-phase architecture), or whether SASE could achieve the same primary benefit simply by customizing **xprompt swarms and agent clans** to suppress notifications for intermediate agents and only notify on designated agents.

### Bottom Line:
1. **Is "better notifications" the only value-add of Goals?**
   **No.** While reducing notification spam is the most immediately felt pain point, Goals introduces three other foundational capabilities that notification silencing cannot provide:
   - **Verification vs. Notification:** SASE currently has binary process completion (`JumpToAgent` tagged `done`), but no concept of a structured *settlement decision* (Review → Verify / Reject & Relaunch / Drop) backed by durable evidence (git commits, test receipts, check-it steps).
   - **Definition of Done as an Agent Steering Force:** Agents without an explicit goal optimize only their immediate local prompt. A bound goal line (`SASE GOAL ⌖...`) and the required `builtin@goal` finalizer force agents to evaluate whether the intended outcome is true before claiming victory.
   - **Project-Level Inventory of Intent:** SASE tracks ephemeral processes (Agents tab), scheduled backlog tasks (Beads), and designs (Plans), but has zero inventory of active, in-flight human intent across machines.

2. **Can customizing xprompt swarms and agent clans replace Goals?**
   **No.** Relying on ad-hoc clan/swarm silencing suffers from severe technical limitations:
   - **Coverage Blind Spot (The 85% Problem):** Swarms and clans account for less than ~15% of multi-agent runs. Over **41%** of weekly runs on athena (841 of 2,048 runs) are Epic phase/land agents (`sase bead work`), which do not use xprompt swarms. Pipe chains, session successors, and ad-hoc queries would continue to spam.
   - **The Dynamic DAG Trap:** In `#research_swarm`, swarms with `critique=true` or `image=true` execute agents *after* the lead (`.final`). Static "notify the lead" rules notify prematurely or fail when execution graphs branch.
   - **The Precedent of `epic_launch_handoff.py`:** SASE already attempted an ad-hoc notification deferral hack for planner agents (`src/sase/bead/epic_launch_handoff.py`), requiring file locks, atomic JSON state swaps, TTL sweeps, and hundreds of lines of fragile plumbing. Duplicating this across swarms, epics, and pipes recreates distributed state bugs without a shared domain model.
   - **Silence is Not Verification:** Even if only the lead notifies, the user still receives a bare unread dot pointing to a transcript, without structured evidence, test receipts, check-it steps, or a rejection/relaunch mechanism.

3. **Is your skepticism justified?**
   **Emphatically yes.** The existing 6-epic, 35-phase roadmap suffers from **universal scope over-engineering**—specifically in **G4 (Drafts & Universal Binding)**:
   - Forcing every single casual question or one-line query to become a machine-local draft goal with LLM compare-and-swap naming, adoption logic, and answer-acknowledgement creates massive cognitive and token overhead (80 tokens + CLI tool calls per turn, plus 25+ answer-ack chores daily).
   - G1 (`sase-1bu`) just landed its initial 7 phases and immediately spawned child epic `sase-1bu.8` to fix 12 distinct edge-case bugs (phantom active goals, uppercase ID forks, corrupt event handling, projection leaks). Expanding this to universal drafts will paralyze velocity.

---

## 2. Comparison Matrix

| Dimension | Path 1: Full Goals (G1–G6 as planned) | Path 2: Clan/Swarm Silencing (Your Question) | Path 3: Scoped Goals (**Recommended Compromise**) |
| :--- | :--- | :--- | :--- |
| **Core Concept** | Distributed ledger + universal binding + gates + TUI tab | Suppress completion notifications on non-lead clan agents | G1 ledger + G2 binding for Epics/Swarms + G3 gates; drop G4/G5 |
| **Phases / Effort** | ~35 phases across 6 epics (~4–6 weeks) | 1–2 small tasks (~2–3 days) | ~15 phases across 3 epics (~2 weeks) |
| **Noise Reduction** | **95%** (all success pings silenced; only claims notify) | **~15%** (swarms quiet; epics, pipes, questions still spam) | **85%** (epics and swarms quieted; claims notify) |
| **Verification Gate** | Yes (`GoalVerify` gate with typed evidence) | **No** (bare unread dot on agent row) | Yes (`GoalVerify` gate on epic/swarm settlement) |
| **Evidence & Check-it** | Yes (commits, test receipts, check-it steps, gaps) | **No** (user inspects raw transcript) | Yes (gathered on claim by lander/lead) |
| **Coverage of Work** | Universal (every turn bound) | Only xprompt swarms and explicit clans | Structured multi-agent work (epics, swarms, explicit `%goal`) |
| **Failure Modes** | High complexity, G4 draft LLM games, verification fatigue | Premature notification on branched swarms, distributed file-lock bugs | None in casual runs (casual runs fail-open/remain unbound) |
| **Sunk Cost Impact** | Leverages G1 | Wastes G1 (abandons completed Rust ledger) | Leverages G1 fully |

---

## 3. Concrete Recommendation: The "Scoped Goals" Pivot

Do **not** build the monolithic 35-phase program, and do **not** fall into the trap of ad-hoc clan notification suppression. Instead, pivot to **Structured Workflows First (Epics & Swarms)**:

1. **Finish Landing G1 Fixes (`sase-1bu.8`):**
   The Rust core domain model, immutable ledger, and CLI fast path are already built and tested. Land the fixes to secure the foundational storage layer.
2. **Re-scope G2 (Deterministic Binding) to Epics and Swarms Only:**
   - Bind epic phase/land agents to the epic's goal via the existing plan `goal_id`.
   - Bind swarm members to a clan goal.
   - **Explicitly drop G4 draft goals from G2:** if an agent has no plan, no epic bead, no clan, and no `%goal`, it runs **unbound (fail-open)**. It pays zero token tax and makes zero draft-naming calls.
3. **Deliver G3 (Claims and `GoalVerify` Gates):**
   - Epic phase workers and swarm researchers have role `contributor` → can only submit `keep_open` (which is **silent**).
   - Land agents and swarm leads have role `owner` → submit `claim` with `@commit` or report artifact refs.
   - A claim fires **one** `GoalVerify` gate with Verify / Reject & Relaunch / Drop.
   - This eliminates **85%+ of all notification spam** without writing a single line of G4 draft code.
4. **Pause and Measure before G4 (Universal Drafts) and G5 (TUI Tab):**
   - Run the scoped system for 2 weeks.
   - Assess whether casual questions actually need goals. If not, cancel G4 permanently and avoid building mechanism ahead of corpus.

The full, detailed report has been registered as artifact `file:explicit:85f938e0a8de02b1fd1f5fe7` and committed to the research sidecar repository.
