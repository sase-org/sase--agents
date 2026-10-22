# Chat History - ace-run (research.47.grk)

- **TIMESTAMP:** 2026-10-09 13:24:23 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.47.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_130507.md`

## Prompt

%id(grk, clan=research.47)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.47.cdx`, `research.47.cld`, `research.47.mus`, `research.47.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the auto-restart design independently: current failure handling, the `,x` dismiss-and-edit flow, and which error patterns are actually restart-safe. First I'll load the research skill and locate the relevant code.

The deep-research coordinator loop doesn't apply here — I'm already the swarm researcher. I'll read SASE memory, glossary, and the live agent-failure path next.

`auto_launch_prefix` is gone from the tree — that matches the live ImportError. Next I’ll map restart/kill-and-edit, notifications, and how agent failures are classified.

There's already `sase agent restart` and a usage-limit drain that relaunches agents. I'll map those plus failure classification, retry, and notifications.

There's already a `source_skew` module for ImportError after editable-source updates. I'll read that next, plus retry vs kill-and-edit.

I have the design: reuse `sase agent restart` (the `,x` path without the edit pause), observe out-of-process, and keep the match set narrow. Writing the independent report next.

The plan is a good idea as a **narrow recovery companion**, not as a generic FAILED-agent auto-retry. Automate `sase agent restart` (that is `,x` then submit without the edit pause), observe from a **fresh** process, match a **harness-import** class, hop **once**, and tell the user with one gold `↻` card.

Report: `sase/repos/research/202610/agent_harness_crash_auto_relaunch/agent_harness_crash_auto_relaunch__grk.md`  
Registered: `research:202610/agent_harness_crash_auto_relaunch/agent_harness_crash_auto_relaunch__grk.md` (`file:explicit:b2a39662e49d26d36b0f6baa`)

**What actually broke.** `auto_launch_prefix` was renamed to `queue_launch_prefix`. A live runner kept old modules in `sys.modules` and then lazily imported the new file. SASE already has preload, wait-path re-exec, and the yellow update gear; preload walks `sase.sdd`/`sase.bead`, not `sase.monitor`, so this hole is real.

**Adjustments I would make**

- Drive `sase agent restart`, not ACE keys. `<ctrl+g>` opens `$EDITOR`; submit is `<enter>`. ACE may itself be stale.
- The dying process cannot recover itself. Observer = sase service + durable proc (same shape as provider drain).
- Match shapes (`cannot import name … from 'sase.*'`, missing module, attribute, `sase_core_rs`, bad magic, torn install files, `code_swap_explanation`). Do not catalog yesterday’s symbol names.
- Exactly-once = one automatic hop. Stamp the FAILED artifact and the successor; never auto-relaunch an auto-relaunched run.
- Batch a swarm into one proc and one notification with `+1`s.
- Beta flag `agent_harness_relaunch`. Wait out an in-flight update and preflight `import sase` so a torn install cannot crash-loop.
- Same epic, prevention first: preload `sase.monitor`.

**Do not** auto-retry provider errors, usage limits (drain already owns those), user kills, OOM, plan/gate failures, or workspace ImportErrors. v1 is a full redo of the stored prompt, not a chat resume.

**Notification.** Sender `agent.harness`, icon `↻`, gold like the update gear, `JumpToAgent` to the **new** row, copy that names the error, the SHAs, the once-rule, and how to undo.
