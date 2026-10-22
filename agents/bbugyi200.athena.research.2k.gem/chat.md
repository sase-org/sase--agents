# Chat History - ace-run (research.2k.gem)

- **TIMESTAMP:** 2026-09-25 16:55:55 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2k.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_162143.md`

## Prompt

%id(gem, clan=research.2k)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2k.cdx`, `research.2k.cld`, `research.2k.grk`, `research.2k.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

There was recently a
failure (30-60 minutes ago) on this machine that caused all sase agents to fail and
required me to restart all affected agents. Can you do some research with the goal of
auditing those failures and the actions that I took to rectify the situation? Continue
this research by exploring the different UX solutions I could consider adding to the TUI
in order to make recovering from these types of failures easier. End your analysis with
a recommended solution. 
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

# Forensic Audit of Recent Systemic Agent Failures & TUI Recovery UX Architecture

**Researcher:** `research.2k.gem`  
**Report Artifact:** [`file:explicit:562998651c00b9df5aa115e8`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/agent_failure_audit_and_recovery_ux__gem.md)  
**Registered Label:** `research:202609/agent_failure_audit_and_recovery_ux__gem.md`  
**File Location:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/agent_failure_audit_and_recovery_ux__gem.md`

---

## 1. Audit of the Failure Incident (2026-09-25 15:09–16:45 EDT)

### 1.1 Root Cause Analysis
The cascading failure that struck all active agents was caused by a **cross-repository wire schema desynchronization between the Rust backend (`sase-core`) and Python frontend/runtime (`sase`)**:

1. **The Core Contract Flip**: At 14:55 EDT, commit `2a0fc2ab` landed in `sase-core` (`feat(core)!: canonicalize agent-session contracts`). This commit canonicalized `agent_session` parameters and bumped several wire schemas:
   - Agent artifact scan wire schema: `9` $\to$ `10`
   - Agent work statistics wire schema: `6` $\to$ `7`
   - Agent launch wire schema: `1` $\to$ `2`
   - Agent cleanup planner schema: `5` $\to$ `6`
2. **The Auto-Upgrade Trap**: At 15:09 EDT, the host ran `sase update -y && sase agent index gc && ace --restart-service`. When agents and monitored commands ran inside numbered workspaces (`sase_<N>`), the workspace `Justfile` recipe `_setup` fast-forwarded their linked checkout `sase/repos/linked/sase-core` to `origin/master` and rebuilt/installed `sase_core_rs` 0.34.73.
3. **The Validation Guardrail Collapse**: Ephemeral workspaces had not yet received the corresponding Python changes. When `tools/validate_sase_core_rs` ran during setup, its contract probe threw:
   ```text
   [validate_sase_core_rs] scan_agent_artifacts probe returned stale schema: got 10, expected 9
   error: recipe `_setup` failed on line 141 with exit code 1
   ```
   Every active monitored command (`--mon`) aborted during `_setup`. In addition, running processes in the host (`sase tui` and `sase agent list`) died or stalled on deserialization schema assertions. Terminating processes left lingering `.git/index.lock` files across active workspaces.

### 1.2 Inventory of Affected Agents
Over a dozen agents across 10+ workspaces collapsed between 15:10 and 15:57 EDT:
- **`0se--0` / `0se--mon`** (workspace 25; `claude_oauth_refresh_retry`)
- **`0sf--0` / `0sf--mon`** (workspace 29; `lease_index_lock_recovery`)
- **`sase-17m.9--mon`** (workspace 12; Epic Phase Bead 17m.9)
- **`0sd--0` / `0sd--mon`** (workspace 18; `agent_header_preview_three_rows`)
- **`sase-19i.2--mon`** (workspace 42; Clan 19i Phase 2)
- **`sase-19o.3--mon`** (workspace 14; Clan 19o Phase 3)
- **`sase-19p.2--mon`** (workspace 44; Clan 19p Phase 2)
- **`sase-17x.13.10.6--mon`** (workspace 24; Clan 17x Phase 6)
- **Dismissed FAILED batch** (`sase-17d.12.2--6`, `0s8--0`, `0rv.w0.f0--2`, `sase-19i.2--1`, `0sa`)

---

## 2. Audit of User Rectification Actions

The user executed a 4-phase recovery operation:

1. **Workspace and Lock Remediation (15:35–15:42)**:
   - Manually pruned stale `.git/index.lock` files in workspaces `sase_47`, `sase_12`, and `sase_25`.
   - Purged corrupted workspace `sase_14`.
   - Launched agent `0sc` to draft an automated lease/lock recovery strategy (`lease_index_lock_recovery.md`).
2. **Premature Continuation Attempt (15:57)**:
   - Attempted to restart/fork `0se--1`, `sase-17m.9--1`, and `0sf--1` from the TUI.
   - Because the underlying Python contract mismatch was still unaddressed, these runs failed immediately during `_setup` validation (`0se--mon-0`, `0sf--mon-0`, `sase-17m.9--mon-0`), causing further session lineage fragmentation (`--1`, `--2`).
3. **Synchronized Rust and Python Contract Fixes (15:38–16:09)**:
   - **`sase-core`**: Landed backwards-compatibility commits `6cb3517` (preserving readability of older artifact indexes) and `2457913` (accepting pre-contract relationship batches).
   - **`sase`**: Authored and landed commit `d86bcc3ac` (`fix(core)!: speak the agent-session core contract`):
     - Bumped Python schema mirrors: scan 10, index 33, cleanup 6, launch 2, gate follow-up 2, session-parent 2, saved-group archive 3.
     - Enforced `agent_session` parameter across all dispatch facades.
     - Updated `tools/validate_sase_core_rs` probes to expect schema 10.
     - Pinned `sase-core-revision.txt` to `2457913`.
4. **Targeted Agent Recovery Waves (16:12–16:45)**:
   - *Wave 1 (16:12–16:15)*: Relaunched `0sd--1`, `sase-19i.2--1`, `sase-19o.3--1`, and `sase-19p.2--1`.
   - *Wave 2 (16:27–16:44)*: Cleaned up and restarted the failed 15:57 attempts (`0se--2`, `0sf--2`, `sase-17m.9--2`, `sase-19p.2--2`).
   - Resumed queued epic phases via `sbd work`.

---

## 3. Current TUI Recovery Limitations

The recovery process exposed four major pain points in the SASE TUI:
1. **Single-Agent Relaunch Bottleneck**: Relaunch actions (`R` for retry, `F` for fork) only operate on the single focused row. For 12 failed agents, the user had to perform 50+ keystrokes: navigate row $\to$ press `R`/`F` $\to$ edit/submit prompt bar $\to$ wait $\to$ repeat.
2. **Marked Agents Asymmetry**: SASE’s `_marked_agents` allows selecting multiple rows, but supports only **kill** (`k`), **dismiss** (`s`), **wait** (`w`), and **revert** (`y`). There is **no bulk retry** and **no bulk fork**.
3. **No Incident Clustering**: Failed agents are scattered across the table; the TUI does not group agents that crashed simultaneously from the same systemic root cause.
4. **Blind Relaunch Hazard (No Pre-Flight Gating)**: The TUI offers no health check before launching. When the user retried agents at 15:57, the TUI dispatched them into an environment doomed to fail, wasting tokens and creating confusing `--1` $\to$ `--2` lineages.

---

## 4. Explored TUI UX Solutions

| UX Option | Description | Pros | Cons |
| :--- | :--- | :--- | :--- |
| **1. Marked-Agent Bulk Operations** | Pressing `R` or `F` with active `_marked_agents` opens a Bulk Relaunch Modal. | Leverages existing marking muscle memory (`m`); full user control over selection. | Requires manual row identification and marking by the user. |
| **2. Incident Triage Banner & Recovery Wizard** | Automatically detects failure bursts ($\ge 3$ failures in 15m), shows a top-level alert banner, and opens a pre-flight verified Recovery Wizard. | **Eliminates hunt-and-seek; hard pre-flight health gate prevents premature restarts.** | Requires sliding-window failure clustering heuristics. |
| **3. Colon Command-Line Palette** | `:agent recover --failed`, `:agent recover --since 45m`, `:agent fork --marked`. | Fast, non-modal, keyboard-first, scriptable. | Low visual discoverability; no interactive pre-flight feedback. |
| **4. Deck Panel Recovery Card** | A contextual card in the Agents Detail deck offering 1-click clan restarts when viewing a failed agent. | Clean contextual integration; scoped to clan/phase. | Does not address cross-clan systemic outages. |

---

## 5. Recommended Solution: Incident-Aware Multi-Agent Recovery Architecture (IMARA)

We recommend a 3-tiered recovery architecture:

### Tier 1: Marked-Agent Bulk Operations (`_bulk_retry_marked_agents` & `_bulk_fork_marked_agents`)
- Bind `R` (when marked) to **Bulk Retry** and `F` (when marked) to **Bulk Fork**.
- Opens a **Bulk Dispatch Modal** allowing the operator to:
  - Toggle between **Fork Continuations** (`#fork:...`) and **Fresh Relaunches** (`allocate_retry_name`).
  - Configure **Staggered Admission** (e.g. 1.5s delay per launch into the runner slot queue to prevent thundering-herd API/resource spikes).
  - Apply global overrides (e.g. model alias, reasoning effort, or queue weight).

### Tier 2: Incident Detection Banner & Pre-Flight Verified Wizard
- A background `FailureClusterWatcher` tracks terminal events in `runs.jsonl`. When $\ge 3$ agents fail within 15 minutes or share an exit error signature (e.g. `_setup` exit 1), ACE displays a sticky alert:
  ```text
  ⚠ INCIDENT DETECTED: 8 agents failed in the last 30m (Signature: Setup) [R: Open Wizard]
  ```
- The **Incident Recovery Wizard** runs an automatic environment pre-flight check before enabling the relaunch action:
  - `validate_sase_core_rs` execution check (ensures Rust/Python schema parity).
  - Active workspace `.git/index.lock` detection.
  - Daemon/service host liveness check.
- **Hard Gate**: If pre-flight fails, the Relaunch button is disabled with an explanatory diagnostic message, directly preventing the pre-fix failure loop experienced in this incident.

### Tier 3: Colon Palette Shortcuts
- Adds `:agent recover --failed` and `:agent recover --incident` for power users seeking fast-path recovery without leaving the keyboard.

---

## 6. Durable Snapshot Registration

The research report has been written and permanently registered in the SASE artifact store:
```bash
sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/agent_failure_audit_and_recovery_ux__gem.md" -l "research:202609/agent_failure_audit_and_recovery_ux__gem.md"
```
- **Artifact ID**: `explicit:562998651c00b9df5aa115e8`
- **Stored Snapshot Path**: `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260925162147/agent_failure_audit_and_recovery_ux__gem-9e578095249e.md`
- **Host Finalizer Status**: Submitted and accepted (`commit` on `sdd:research`).
