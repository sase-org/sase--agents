# Chat History - ace-run (research.47.mus)

- **TIMESTAMP:** 2026-10-09 13:18:20 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.47.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_130507.md`

## Prompt

%id(mus, clan=research.47)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.47.cdx`, `research.47.cld`, `research.47.grk`, `research.47.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

A
number of sase agents just failed on this machine with the following error:
`ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`

- This error was clearly caused by updating sase while agents were running, which is
  something I would like to support.
- I would like to start automatically detecting errors like this and attempting to
  automatically resolve the issue by dismissing and re-launching the sase agent that
  failed.
- We should try to restart an agent exactly once when a detected error pattern matches.
  Think hard about which error patterns we should check for.
- This operation should be very similar to what happens when the user selects a failed
  agent on the "Agents" tab, uses the `,x` keymap to dismiss and edit it, and then
  submitting the prompt (e.g. via the `<ctrl+g><enter>` keymap) that loads in the prompt
  input widget without modifying it.
- We should send an excellent and thorough sase notification to the user when we restart
  a failed agent like this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete and registered.

**Top finding:** auto-relaunch is worth building, but not as an ImportError-regex watcher — the winning design makes version skew a first-class explicit error (spawn-time version stamp checked at each delivery) and relaunches exactly once on that, reusing the existing headless `,x` equivalent (`prepare_kill_and_edit_prompt` + `plan/execute_agent_restart`), gated on update quiescence, with digest notifications.

Report written to [auto_relaunch_failed_agents_update_skew__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/auto_relaunch_failed_agents_update_skew__mus.md) and registered as durable snapshot `file:explicit:d472519864f411b1304dafb5` (`research:202610/auto_relaunch_failed_agents_update_skew__mus.md`).

Key verified facts: `auto_launch_prefix` occurs zero times in `src/` (old-bytecode/new-module skew confirmed); `src/sase/monitor/store.py` already treats `ImportError` as environmental in three catch sites; the `,x` rewrite (forced name reuse, clan/agent-session repair, `KillAndEditPromptError` refusals) lives headless-safe in `src/sase/agent/relaunch_prompt.py`; `notify_axe_error_digest` is the notification precedent to follow. Adjustments I call out explicitly: add a quiescence gate, classify failures structurally at catch sites instead of matching strings, restrict eligibility to launch/infrastructure failures, reuse the `,x` eligibility predicate, and add a fleet circuit breaker. I worked independently and did not consult any peer report.

Declaration accepted for the `sdd:research` report. Host will commit after this turn.
