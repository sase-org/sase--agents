# Chat History - ace-run (research.2y.gem)

- **TIMESTAMP:** 2026-09-30 06:44:47 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2y.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%id(gem, clan=research.2y)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2y.cdx`, `research.2y.cld`, `research.2y.grk`, `research.2y.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently store
too many prompts in prompt history (see the ~/tmp/screenshots/20260930_062115.png
screenshot for an example of a prompt that likely shouldn't have been stored).

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.

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

# Research Report: Restricting Prompt History to Human-Authored Intent

**Researcher:** `research.2y.gem`  
**Report File:** [`prompt_history_user_intent_scoping__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/prompt_history_user_intent_scoping__gem.md)  
**Registered Artifact:** `research:202609/prompt_history_user_intent_scoping__gem.md` (`file:explicit:401928f07f9559cdf97ca1bb`)

---

## 1. Empirical Findings & Root Cause Analysis

An investigation of the local prompt history store (`~/.sase/prompt_history/`) and the provided screenshot (`~/tmp/screenshots/20260930_062115.png`) confirms that the prompt history store is experiencing acute data pollution:

- **Store Volume & Machine Ratio:**
  - **Overall:** **62.6%** of all stored prompts (7,251 out of 11,584 records across `2607.json`–`2609.json`) are machine-generated.
  - **Current Month (`2609.json`):** **75.9%** (2,869 out of 3,781 prompts) are machine-generated. More than 3 out of every 4 prompts recorded in September 2026 originated from automated jobs rather than a human user.
  - **Top Dominant Chips:** `#bd/work_phase_bead` accounts for 4,921 rows; `#bd/land_epic` accounts for 1,805 rows. Together, these two automated epic dispatch markers make up **over 58% of the entire database**.
  - **Payload Bloat:** Individual routine split chops embed multi-file diff briefs, reaching 30 KB to 100 KB per prompt and inflating store size to nearly 7 MB.

- **Screenshot Analysis:**
  The burst of entries at `09-30 01:58` (`+4 +sase`, `+3 +sase`, `+2 +sase`) corresponds to `sase bead work sase-1d5` (the 8-phase epic for public bead attachments). When `launch_planned_bead_work_agents` ran, it recorded the full multi-phase prompt **plus all 8 phase segments** individually due to `record_segments=True` defaulting in `add_or_update_prompt`. Similar cascades occurred at `09-29 20:34` (`sase-1cx`: 9 entries) and `09-29 17:05` (chop `toobig-4n`: 11 entries).

- **How Swarm Member Prompts Leak:**
  Under the standard path, `#research_swarm` is recorded as a single unexpanded string. However, member prompts leak in two specific situations:
  1. *Provider Launch Guard in TUI:* When a provider is disabled or flagged, [`_launch_provider_guard.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/ace/tui/actions/agent_workflow/_launch_provider_guard.py#L398) rewrites `launch.prompt` with `\n---\n.join(unit.prompt for unit in surviving)` before running `sase run`. This exposes the expanded researcher prompts to [`add_or_update_prompt`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/history/prompt_store_mutations.py#L36), which saves both the joined multi-prompt and every single researcher's segment.
  2. *Single-Agent Swarm Expansions:* When an xprompt swarm expands to a single slot, [`launch_cwd_agents.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/agent/launch_cwd_agents.py#L198) overwrites `query` with `expanded_segments[0]`, recording the rendered agent body rather than the `#swarm` command.

- **The Missing Link in Commit `eaa4aa4aa7` (`sase-1cj.2`):**
  On Sep 29, 2026, commit `eaa4aa4aa7` introduced `PromptOrigin = Literal["typed", "generated"]`. However, it used `origin` solely to filter n-grams for the Rust next-word prediction engine (`PromptPredictionCorpus`). It never connected `origin` to write-time suppression in `add_or_update_prompt`, nor did it filter `origin` in `prompt_catalog.py` or the TUI History tab.

---

## 2. Critique of the Plan

### Is this a good idea?
**Yes.** Prompt history was designed as a human recall and replay buffer (for the TUI History tab, `sase prompt run`, and Ctrl+T prediction), not an execution audit log. SASE already has dedicated audit stores for background work (`sase proc`, `sase agent`, `sase tool`, and `chop_agents.json`). Storing automated background runs in prompt history destroys the signal-to-noise ratio for human interactive workflows.

### Evaluation of Alternatives
1. *Display-Only Filtering (Keep writing to disk, hide in UI):* **Rejected.** Disks and memory would continue to bloat with 100 KB machine payloads, JSON parsing would remain sluggish, and the root cause would be unaddressed.
2. *Pure Write-Side Suppression (Stop writing going forward):* **Insufficient on its own.** While it protects future prompts, it leaves 7,251 existing machine prompts in `~/.sase/prompt_history/`, meaning the TUI History tab would remain flooded for weeks or months until old shards age out.
3. *Recommended Approach:* **Holistic Hybrid.** Suppress machine prompts at write time, shield catalog reads by default (`include_generated=False`), and supply a one-time pruning utility (`sase prompt prune --generated`).

---

## 3. Recommended Adjustments to the Requirements

1. **Widen "Routines" to "All Machine-Generated Prompts (`origin == 'generated'`)":**
   Non-routine machine triggers (CLI `sase bead work`, `sase plan approve`, autonomous agent subagents with `SASE_AGENT=1`, and restart executors) produce identical clutter. The rule should be: *no prompt with `origin == "generated"` or `is_chop_launch_env(env)` is ever saved to prompt history.*
2. **Decouple Stored Intent from Execution Payload:**
   Ensure `launch_agents_from_cwd` and `PendingLaunch` decouple the runtime execution query from the recorded user prompt. When swarms expand or provider guards filter units, the user's unexpanded intent string must be preserved for history.
3. **Include Read-Side Shielding and One-Time Storage Pruning:**
   Add default exclusion of `origin == "generated"` and legacy `looks_generated` rows to [`prompt_catalog.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/history/prompt_catalog.py) (`load_prompt_record_page`), giving the TUI immediate visual relief. Provide `sase prompt prune --generated` to allow users to reclaim ~5 MB of disk space immediately.

---

## 4. Recommended Implementation Steps

1. **Write Gating ([`prompt_store_mutations.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/history/prompt_store_mutations.py)):**
   - Update `_effective_prompt_origin` to check `is_chop_launch_env(env)` and map any routine environment to `"generated"`.
   - In `add_or_update_prompt` and `record_failed_launch_prompt`, check `if effective_origin == "generated": return` (while keeping `record_prompt_placeholders(text)` so user tags remain discoverable).
2. **Swarm Intent Preservation ([`launch_cwd_agents.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/agent/launch_cwd_agents.py) & [`_launch_provider_guard.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/ace/tui/actions/agent_workflow/_launch_provider_guard.py)):**
   - For single-agent swarm expansions, pass `submitted_query` as `history_query` so the authored `#swarm` command is preserved rather than the rendered slot prompt.
   - In `_launch_provider_guard.py`, retain `launch.submitted_prompt` when rewriting `launch.prompt` with surviving units.
   - In `launch_cwd_bead_work.py`, ensure `record_segments=False` and `origin="generated"`.
3. **Read Shielding & Pruning ([`prompt_catalog.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/history/prompt_catalog.py) & [`cli_maintenance.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/src/sase/prompt/cli_maintenance.py)):**
   - Add `origin` to `PromptHistoryRecord`. In `_record_matches_filters`, filter out `origin == "generated"` and `looks_generated(record.text)` when `include_generated` is False (the default).
   - Implement `sase prompt prune --generated` to purge legacy machine rows from existing shards under the writer lock.

---

## 5. Artifact & Turn Finalization

- **Research Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/prompt_history_user_intent_scoping__gem.md`
- **Artifact Snapshot:** Created with `sase artifact create` under label `research:202609/prompt_history_user_intent_scoping__gem.md` (`id: explicit:401928f07f9559cdf97ca1bb`).
- **SASE Final Declaration:** Submitted and accepted for dirty repository `sdd:research` (`repo-8ea1db3f42bd`) with Conventional Commit message:
  `docs(research): analyze prompt history scoping for swarms and routines`.
