# Chat History - ace-run (research.4u.gem)

- **TIMESTAMP:** 2026-11-15 17:01:26 EST
- **MODEL:** agy/gemini-4-hydrogen-xhigh
- **AGENT:** research.4u.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261115_164459.md`

## Prompt

%id(gem, clan=research.4u)
%m:agy/gemini-4-hydrogen-xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4u.cdx`, `research.4u.cld`, `research.4u.grk`, `research.4u.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It doesn't seem like agent hijacks are working correctly. See the
~/tmp/screenshots/20261115_164112.png screenshot, which was taken on the apollo machine,
for context. Agent hijacks should work on as many types of sase turns (in as many
states) as possible. I would like to fix this issue and make agent hijacks much more
resiliant / dependable in general.

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

The research report has been written and registered as a durable SASE artifact:

- **Report:** [agent_hijack_resilience_and_turn_coverage__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/agent_hijack_resilience_and_turn_coverage__gem.md)
- **Registered Artifact:** `id: explicit:d8fbfcf4f5f31eb42dc440f6` (`ref: file:explicit:d8fbfcf4f5f31eb42dc440f6`, snapshot at [agent_hijack_resilience_and_turn_coverage__gem-eaa7da1c87b8.md](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261115164507/agent_hijack_resilience_and_turn_coverage__gem-eaa7da1c87b8.md), label `research:202611/agent_hijack_resilience_and_turn_coverage__gem.md`)
- **Final Declaration:** Submitted and accepted (`commit` for `sdd:research`).

### Key Findings

1. **Why Agent Hijacks Fail in the Screenshot (`20261115_164112.png`, `tailnet-t.10`):**
   - **TUI rejects almost all real agents:** [`agent_can_offer_hijack()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/actions/agents/_hijack_action.py#L23) hard-requires `AgentType.RUNNING`, whereas `workflow_state.json` (`appears_as_agent: True`) causes `dedup_running_vs_workflow()` to surface `AgentType.WORKFLOW` instead.
   - **Collapsed session container & missing Enter-key mirroring:** Hijack checks the collapsed root container (`--plan`, already `completed`) rather than delegating to active member turn(s) (`--5` and `--mon-3`), and [`_mirror_root_from_child()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/models/_agent_status_apply.py#L49-L98) omits `hijack_record` and member identity fields needed when pressing `⏎`.
   - **`"hijack"` capability is wiped at bootstrap & omitted on follow-ups:** [`_write_bootstrap_agent_meta()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/axe/run_agent_runner_bootstrap.py#L150-L160) writes `runner_capabilities: ["hijack"]`, then [`extract_directives_and_write_meta()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/axe/run_agent_runner_bootstrap.py#L467) overwrites `agent_meta.json` using [`preserved_agent_metadata()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/axe/run_agent_directive_metadata_preserved.py), omitting `"runner_capabilities"`. [`create_followup_artifacts()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/axe/run_agent_helpers_artifacts.py) omits it too, triggering Rust [`eligibility.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core/crates/sase_core/src/agent_hijack/eligibility.rs#L55-L56) `missing_capability`.
   - **`finalizing` + simultaneous `--mon-3`:** Even past bugs 1–3, Rust [`eligibility.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/linked/sase-core/crates/sase_core/src/agent_hijack/eligibility.rs#L28-L36) refuses `finalizing` and `monitor_turn`, and there is no lane-level atomic preemption across finalizing `--5` and co-active `--mon-3`.
   - **Downstream schema drift:** [`_stop_target.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/hijack/_stop_target.py#L78-L89) reads wrong keys (`agent_llm_provider`, `agent_effort`, numeric `booted_at`, `gate_turn`) instead of the keys written by [`run_agent_directive_metadata_build.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/axe/run_agent_directive_metadata_build.py#L84-L89) (`llm_provider`, `reasoning_effort`, ISO `booted_at`, `turn_kind`), breaking concrete target resolution (`invalid_model_target`). [`_stop_evidence.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/agent/hijack/_stop_evidence.py#L77) also misses `opened_linked_workspaces.json` / `opened_siblings.json` and `LinkedRepoResolution` dict entries.

2. **Requirement Critique & Adjustments:**
   - **Don't force every turn/state into workspace-holding `⏏ HIJACKED` custody:** Pre-workspace `WAITING`/`QUEUED` (`ws #0`), idle human gates (`PLAN`/`TALE`/`EPIC`/`QUESTION`), and unisolated `home_mode` turns lack exclusive numbered workspace diffs/claims or already await human review.
   - **6 concrete adjustments** in the report: (1) lightweight Edit/Cancel (no workspace lock) for `ws #0` waiting turns; (2) keep idle human gates excluded (redirect to `⏎` review) while supporting stuck `settling` gates; (3) hijack `Monitor` turns with a monitor-specific recovery menu (Hand off Diff+Log to Agent / Restart / Dismiss, hiding LLM Escalate/`#fork:`); (4) hijack at the **active workspace-lane** level (`--5` finalizing + `--mon-3` active together); (5) make `finalizing`/`handoff` preemptible after a short bounded drain with an explicit recovery warning; (6) remove Python's separate TUI filter so Rust eligibility is the single authority across TUI and CLI.

3. **Recommended Phased Solution:** Detailed in Section 5 of [the full report](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/agent_hijack_resilience_and_turn_coverage__gem.md) (P0 immediate bugfixes & metadata/TUI/Rust alignment, P1 expanded turn/state support & lane atomicity, P2 typed metadata schema contract, signal/claim race auditing, and full-stack bootstrap+TUI integration tests).
