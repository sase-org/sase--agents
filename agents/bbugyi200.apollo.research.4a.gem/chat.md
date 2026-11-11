# Chat History - ace-run (research.4a.gem)

- **TIMESTAMP:** 2026-11-11 16:51:19 EST
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4a.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261111_163622.md`

## Prompt

%id(gem, clan=research.4a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4a.cdx`, `research.4a.cld`, `research.4a.grk`, `research.4a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of helping me determine the next 7 task beads for
this project that would be most impactful if worked right now? End your analysis with a
ranked list of these 7 task beads (with strong justification for each). 
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

### Research Summary: Top 7 Highest-Impact Task Beads to Work Right Now

As researcher `gem` in this 5-researcher swarm, I have independently investigated the SASE project task backlog (comprising 1,427 total task beads, with 410 open and unblocked in `ready` status). 

The analysis cross-referenced active in-progress epics (such as CI contention repair in [`sase-1rq`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/AGENTS.md), update-skew handling in [`sase-1ra`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/AGENTS.md), and release train stabilization in [`sase-1s7`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/AGENTS.md)) to guarantee that none of the proposed beads collide with ongoing epic phases or duplicate active work.

The complete research report has been written to:
- **File**: [`next_seven_highest_impact_task_beads__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/next_seven_highest_impact_task_beads__gem.md)
- **Snapshot Artifact Ref**: `file:explicit:e6831b39d8f44bf94ab58764` (`research:202611/next_seven_highest_impact_task_beads__gem.md`)

---

### Ranked List of the Next 7 Highest-Impact Task Beads

| Rank | Bead ID | Task Type | Size | Core Subsystem | Summary Title & Primary Justification |
| :---: | :---: | :---: | :---: | :---: | :--- |
| **1** | **`sase-1qm`** | `bug` | Large | Finalizers / Completion | **Host completion refuses an unchanged prepared-completion intent with `stale_worktree_fingerprint` after a passing check**<br>• *Justification*: Prepared completion (`sase monitor start -f`) is SASE's primary mechanism for zero-turn monitor landings. In this bug, a green 30-minute check (`just check`) is discarded at host evaluation time due to false-positive fingerprint divergence across linked repos, forcing unnecessary agent recovery turns and burning compute. Fixing this in `sase-core` restores automated completion reliability across the fleet. |
| **2** | **`sase-1ot`** | `bug` | Large | Security / Compliance | **Rotate and purge the 27 historical secret-scanner hits in public `sase--agents` history (owner-approved remediation)**<br>• *Justification*: 27 secret scanner hits remain in the public commit graph of `sase--agents`. The repository owner already approved credential rotation and history rewriting via notification gate `custom-57bc7a62`. With approval already on record, executing this unowned bead immediately eliminates an active public security and compliance exposure. |
| **3** | **`sase-1s4`** | `bug` | Large | Test Suite / VCS Integrity | **Find the test that leaves a stale lock in the real checkout**<br>• *Justification*: Observed in recent contention runs (`2026-11-08`), a test case escapes its sandbox and leaves an unowned `.git/index.lock` in the real repository checkout. This immediately wedges host-completion finalizers, `sase stitch create`, and all subsequent Git mutations in that workspace until manually recovered. Identifying the test and extending `_checkout_leak_guard.py` eliminates silent workspace wedging. |
| **4** | **`sase-1s2`** | `bug` | Small | AXE Runtime / Teardown | **Runner module imports overwrite the process SIGTERM handler**<br>• *Justification*: Top-level module code in `src/sase/axe/run_agent_runner.py:87` and `mentor_runner.py:30` overwrites `signal.signal(signal.SIGTERM, ...)`. Importing these modules causes pytest workers to ignore `SIGTERM`, causing hung tests, zombie `xdist` processes, and un-killable runners. This is a high-ROI quick fix (`small`) that removes a widespread test harness pollution vector. |
| **5** | **`sase-1ce`** | `bug` | Small | ACE TUI / Prompt Safety | **Prompt `$EDITOR` temp file is deleted when the editor exits non-zero, losing typed prompt**<br>• *Justification*: In `src/sase/ace/tui/actions/agent_workflow/_editor.py`, if `$EDITOR` exits non-zero (e.g. `:cq`, syntax error, shell disconnect, killed process), the temporary file is unconditionally deleted in `finally`. Everything the user typed is permanently wiped out, directly violating SASE's core architectural guarantee: *"Never lose a user prompt"*. Preserving the buffer in prompt stash recovery restores prompt safety for human operators. |
| **6** | **`sase-1db`** | `bug` | Medium | Storage / Data Privacy | **`attachments-private` store never verifies an existing remote is private before pushing attachment bytes**<br>• *Justification*: `preflight_sidecars` in `src/sase/sdd/_sidecar_init.py` only validates visibility if creating a brand-new remote. If an existing remote is public, SASE assumes it is private and pushes private attachment bytes to GitHub while the UI labels it `(private)`. Enforcing remote visibility checks prevents confidential attachment data leaks. |
| **7** | **`sase-1re`** | `bug` | Medium | Scheduler / Bead Ownership | **Done monitor with stale `followup_pending` owns its bead forever**<br>• *Justification*: When a monitor turn finishes with `followup_pending=true` but the follow-up agent fails to spawn, `sase-core`'s stranded work classifier classifies the bead as actively owned by the monitor rather than `STRANDED`. ACE never alerts the user, the recovery reconciler never triggers, and downstream dependent agents remain parked forever. Fixing `owner_kind` unblocks abandoned bead lifecycles. |

---

### Implementation Sequencing Recommendation

1. **Wave 1 (Immediate Quick Wins - Day 1)**: `sase-1s2` (SIGTERM import side effect) and `sase-1ce` (editor prompt preservation).
2. **Wave 2 (Security & Privacy Hardening - Day 2)**: `sase-1ot` (purging 27 public secret hits) and `sase-1db` (remote privacy verification).
3. **Wave 3 (Completion & Fleet Reliability - Days 3-4)**: `sase-1qm` (prepared-completion worktree fingerprint fix), `sase-1s4` (checkout `.git/index.lock` leak attribution), and `sase-1re` (stranded monitor classifier).
