# Chat History - ace-run (research.4u.cdx)

- **TIMESTAMP:** 2026-11-15 17:01:31 EST
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.4u.cdx
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261115_164459.md`

## Prompt

%id(cdx, clan=research.4u)
%m:gpt-6-astra %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 5-researcher swarm.
The other researchers, `research.4u.cld`, `research.4u.grk`, `research.4u.mus`, `research.4u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

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
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
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

I’ll trace the hijack lifecycle, inspect the screenshot, and evaluate how recovery should work across turn types and states. I’ll research independently, then write and register a report ending in `__cdx.md`.


I’m using `sase_memory_read` and `sase_repo` to review the relevant design context and linked Rust core, plus `sase_artifact` to register the finished report.


The screenshot’s warning comes from the TUI’s eligibility check, before the stop protocol runs. That check excludes monitor and gate turns and requires a workspace number and PID. The selected session shows a monitor among its newest turns; I’m checking how the session row chooses its target and where the backend imposes further limits.


The backend confirms that this is broader than a missing TUI action: it explicitly rejects monitor turns, gate turns, waiting agents, home-mode runs, and finalizing turns. There is already substantial recovery machinery worth preserving. I’m focusing on how to extend it without losing workspace custody or allowing an old continuation and a recovery agent to launch together.


The isolated probes reproduced several reliability gaps: a session row can display `RUNNING` while its selected object is ineligible; separate hijack IDs can target the same run; and a failed intent-marker write does not prevent termination. A simulated failure after pinning also left the pin without its recovery record. These tests used temporary records and mocked process control.


A further probe found that hijack snapshots skip the structured linked-repository metadata produced by current launchers; the existing end-to-end fixture uses plain path strings instead. My recommendation is taking shape: extend the durable recovery protocol with session-aware targeting and turn-specific stop handlers, and repair custody and reconciliation gaps before widening eligibility.


The report is written. It recommends extending the existing protocol, with explicit behavior for each turn type, and distinguishes reproduced defects from race risks that still need tests. I’m registering the durable snapshot and checking the final repository declaration.


Registration succeeded, and the source report remains in the requested directory. Only the research report changed. I’m using `sase_final` to declare it for the host-managed commit.


Wrote the independent [research report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202611/dependable_agent_hijacks_across_turn_lifecycles__cdx.md).

It identifies the session-selection mismatch and reproduced reliability gaps. Recommendation: extend the durable recovery protocol with session-aware targeting and turn-specific interruption handlers.

Registered [snapshot `explicit:560090c8048c199ecabf5ba7`](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261115164459/dependable_agent_hijacks_across_turn_lifecycles__cdx-6b44bc01a346.md). Source retained.
