# Chat History - ace-run (research.4n.gem)

- **TIMESTAMP:** 2026-10-16 11:24:33 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4n.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_110522.md`

## Prompt

%id(gem, clan=research.4n)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.4n.cdx`, `research.4n.cld`, `research.4n.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to start making it fine for an agent to be launched using the `%id`
directive's `bead=<bead>` input even when `<bead>` is already closed.

- Currently, the sase agent just fails when this is the case which is annoying since I
  often restart sase agents using the `,x` keymap on the "Agents" tab after, for
  example, an error occurs that causes the agent to fail for some reason (sometimes the
  agent or the finalizer has already closed the bead at this point).
- We should make sure to add some kind of recognizable, timestamped note or annotation
  of some sort to the bead so there is a clear audit trail when we do this though.

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

# Research Summary: Relaunching SASE Agents on Closed Beads via `%id(bead=...)`

**Researcher:** `research.4n.gem` (Gemini)  
**Report File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/relaunching_agents_with_closed_beads__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/relaunching_agents_with_closed_beads__gem.md)  
**Durable Artifact Snapshot:** `research:202610/relaunching_agents_with_closed_beads__gem.md` (`file:explicit:c99788514db9d87ee92fa482`)

---

## 1. Executive Summary & Problem Diagnosis

When an agent fails late in its turn—such as during post-commit verification, git push, or patch packaging—the assigned bead may have already been closed (either by the agent running `sase bead close` or by the host completion finalizer executing `sase final submit` with `bead_action: close`). 

When you restart that agent using the `,x` (kill-and-edit) keymap on the TUI's "Agents" tab, SASE reconstructs the prompt:
```text
%id(!agent_name, bead=sase-xxx) <prompt body...>
```
When submitted, SASE abruptly crashes before launching the model:
```text
RuntimeError: Failed to claim bead 'sase-xxx' for agent 'agent_name': cannot claim closed bead for agent launch: sase-xxx
```

### Why It Fails Today
Tracing through the architecture revealed the exact failure mechanism:
1. **Python Launch Promotion**: In [`src/sase/axe/run_agent_runner_launch.py:_promote_bead_claim_at_launch`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_launch.py#L210-L245), SASE calls [`claim_bead_for_agent_launch`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_bead.py#L43-L144).
2. **Forced Reuse Check**: In [`src/sase/bead/force_reuse.py:issue_retains_force_reuse_owner`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/bead/force_reuse.py#L21-L34), SASE requires `issue.status is Status.IN_PROGRESS`. Because the bead is `CLOSED`, it rejects owner retention and delegates to `project.claim_for_agent_launch(bead_id, agent_name)`.
3. **Rust Core Barrier**: In `sase-core` ([`crates/sase_core/src/bead/mutation/claims.rs:107-115`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead/mutation/claims.rs#L107-L115)), Rust executes `run_claim_launch`:
   ```rust
   let current = view.get(issue_id)?;
   if current.status == StatusWire::Closed {
       return Err(BeadError {
           kind: "closed".to_string(),
           message: format!("cannot claim closed bead for agent launch: {issue_id}"),
       });
   }
   ```
4. **Finalizer Contrast**: In contrast, SASE's completion finalizer policy in `sase-core` ([`crates/sase_core/src/bead_action/policy.rs:138-143`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead_action/policy.rs#L138-L143)) *already* considers a closed bead safe and idempotent (`CloseIdempotent`). The only subsystem blocking this workflow is the launch admission claim barrier in `run_claim_launch`.

---

## 2. Critique of the Plan

### 2.1 Is It a Good Idea?
**Yes, in spirit, but with critical architectural constraints.**
The developer friction of having to leave the TUI, drop into a separate terminal, run `sase bead open <id>`, and then re-trigger `,x` is a major usability papercut. Eliminating it aligns with SASE's focus on smooth agent lifecycle management.

However, an unconstrained, blanket permission that allows *any* prompt containing `bead=<id>` to launch against a closed bead carries significant architectural hazards.

### 2.2 Should the Bead Stay Closed During Execution? (No!)
A naive implementation might simply bypass the claim mutation and allow the agent to run while leaving the bead in the `closed` status. **This is fundamentally broken for four reasons**:
1. **Agent Prompt Invariant**: SASE core instructions ([`sase/memory/sase_beads.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/memory/sase_beads.md)) explicitly instruct the model: *"A bead you were launched to work on is already in_progress before you read your prompt."* An agent reading its assigned bead via `sase bead read $SASE_BEAD_ID` will see `status: closed` with `resolution: done`, leading the LLM to conclude that the task is finished and exit or submit an empty declaration.
2. **Dependency Gate Breakage (`%wait`)**: In [`src/sase/agent/launch_admission_runtime.py:492`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/agent/launch_admission_runtime.py#L492), `%wait(bead=<id>)` resolves when `status == "closed"`. If the bead stays `closed`, any waiting downstream agents will immediately dispatch and run concurrently with the retried agent, destroying serial ordering.
3. **Failure Masking**: If the retried agent crashes or is killed midway through, the bead remains marked `closed` (`done`), falsely signaling that work was delivered.
4. **Concurrency Claims**: A `closed` bead has no active assignee or `in_progress` lock, inviting collisions from other automation.

**Verdict**: Launching an agent on a closed bead **must transition the bead to `in_progress` (reopen it)** and assign it to the new agent.

### 2.3 The Stale Replay Hazard
Developers frequently recall commands from history (`sase prompt replay` or up-arrow). If bare `%id(bead=sase-xxx)` silently reopens closed beads without restriction, replaying a prompt from 3 months ago could inadvertently resurrect a completed bead.

**Requirement Adjustment**: Reopening must be authorized by **explicit intent**:
- **Forced Reuse (`%id(!name, bead=<id>)`)**: Automatically allowed (this is what `,x` produces).
- **Bare `%id(bead=<id>)`**: Fails with a descriptive error guiding the user to use forced reuse (`!`) or `sase bead open`.

### 2.4 Hierarchical Invariants (Parent Epics)
In SASE, *"Closing never cascades... `sase bead open <id>` reopens a bead and every closed ancestor above it."* If `<bead>` is a phase bead of an already-closed epic, reopening the phase bead **must walk and reopen closed ancestor epics** (using [`reopen_closed_ancestors_via_view`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead/mutation/close_remove.rs#L650-L690)) to prevent invalid trees (closed epics holding open/in-progress phases).

---

## 3. Recommended Audit Trail Design

To satisfy your requirement for a clear, recognizable, timestamped audit trail without adding new out-of-band files, we leverage SASE's existing dual-layer audit architecture:

1. **Structural Metadata (`close_history`)**:
   - Add a new enum variant `AgentLaunch` to [`BeadReopenCauseWire`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead/wire.rs#L573-L589) in Rust, and mirror it as `ReopenCause.AGENT_LAUNCH` in [`src/sase/bead/model.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/bead/model.py#L36-L46).
   - When claimed, `archive_close_metadata` moves `closed_at`, `close_reason`, and `resolution` into `close_history`, stamping `reopened_via = BeadReopenCauseWire::AgentLaunch` and `reopened_by = agent_name`.
   - Update [`src/sase/bead/reopen_presentation.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/bead/reopen_presentation.py#L37-L49) so the TUI and CLI display:
     `Reopened 2026-10-16T15:20:00Z for agent launch by @agent.retry_1`.
2. **Human-Readable Work Log (`notes`)**:
   - In `run_claim_launch`, automatically append an attributed note to the bead's append-only work log:
     ```text
     [AGENT_RELAUNCH] Reopened closed bead (previously closed at 2026-10-16T15:10:00Z with resolution='done') for agent launch 'agent.retry_1'.
     ```
   - This ensures that anyone inspecting `sase bead show`, `sase bead read`, or the TUI bead details panel immediately sees the provenance and explanation for why the bead was reopened.

---

## 4. Recommended Implementation Blueprint

Following Rule 1.3 (Rust Core Backend Boundary), domain mutations live in `sase-core`, while Python acts as the adapter:

1. **Rust Core (`crates/sase_core`)**:
   - Add `AgentLaunch` to `BeadReopenCauseWire`.
   - Extend [`claim_for_agent_launch`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead/mutation/claims.rs#L24-L39) with `allow_reopen: bool`.
   - In `run_claim_launch`:
     - If `current.status == StatusWire::Closed` and `allow_reopen`:
       - Archive previous close metadata (`archive_close_metadata(&mut issue, &now, BeadReopenCauseWire::AgentLaunch, Some(agent_name))`).
       - Reopen closed ancestors ([`reopen_closed_ancestors_via_view`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/linked/sase-core/crates/sase_core/src/bead/mutation/close_remove.rs#L650-L690)).
       - Append the `[AGENT_RELAUNCH]` audit note to `issue.notes`.
       - Set `issue.status = StatusWire::InProgress` and `issue.assignee = agent_name`.
       - Stage events and commit atomically.
   - Update PyO3 bindings in `crates/sase_core_py/src/beads/mod.rs`.
2. **Python Facade & Launch Runner (`sase`)**:
   - Update [`src/sase/core/bead_mutation_facade.py:claim_for_agent_launch`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/core/bead_mutation_facade.py#L251-L268) and `BeadProject`.
   - In [`src/sase/axe/run_agent_runner_launch.py:_promote_bead_claim_at_launch`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_launch.py#L210-L245), pass `allow_reopen=(bootstrap.force_reuse_bead_association is not None)`.
   - Because `,x` always sets forced reuse (`%id(!name, bead=...)`), this immediately resolves the `,x` restart friction without requiring changes to prompt bar macros or TUI keymap handlers.

---

## 5. Artifact Delivery

The comprehensive research report has been written, verified, and registered as a durable artifact snapshot:
- **Report Location:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/relaunching_agents_with_closed_beads__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/relaunching_agents_with_closed_beads__gem.md)
- **Artifact Ref:** `file:explicit:c99788514db9d87ee92fa482` (`research:202610/relaunching_agents_with_closed_beads__gem.md`)
- **Finalizer Declaration:** Submitted and accepted (`sase final submit`).
