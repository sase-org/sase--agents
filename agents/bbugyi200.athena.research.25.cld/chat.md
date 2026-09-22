# Chat History - ace-run (research.25.cld)

- **TIMESTAMP:** 2026-09-21 18:50:36 EDT
- **MODEL:** claude/opus
- **AGENT:** research.25.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_182824.md`

## Prompt

%id(cld, clan=research.25)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.25.mus`, `research.25.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

sase agents are constantly running
commands that take a long time to finish and then running some kind of internal monitor
or something and dying. I think this is likely happening because these agents don't
understand that they are running in headless mode and thus will not have another turn
and cannot use certain skills / internal tools.

Can you help me audit recent sase agent runs that exited early because of this, diagnose
the true root cause(s), and think hard about what the most appropriate solution to this
problem is? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

I'm reading SASE's Claude provider code to see what already guards against headless-mode waits. Next I'll pull the recent agent transcripts to find runs that died this way.

Still mapping where SASE stores per-agent run artifacts, so I can scan recent runs for native Monitor/background-task usage.

Found the per-run `tool_calls.jsonl` records. Now checking their format so I can scan the last week of runs for native Monitor/background-Bash calls and `sase monitor start` handoffs.

Now running a scan across all projects' agent runs from Sept 14–21, tallying native Monitor/background tools, `sase monitor start` handoffs, and outcomes by provider.

Most runs lack `done.json`, so I'm classifying each run's ending from its own artifacts instead: final declaration, monitor/plan/gate handoff, user kill, or silent exit.

The memory confirms the design: monitoring kills the starter agent and a follow-up resumes. So I need to separate intended handoffs from real silent deaths. Examining the "no_final" runs now.

I'm now pulling monitor records straight from `sase monitor list`, which gives command, duration and follow-up outcome for every handoff in the window.

The Codex "died" cases were actually usage-limit failures mid-poll, not confusion about headless mode, though the in-turn polling did burn quota. Checking Grok's pre-handoff behavior now.

`just check` via ToolRun: median 4.5 min, p90 34 min, max 135 min, and nearly all the variance sits in the scoped test stage. Checking current host load and agent concurrency for context.

Now checking the Claude side: what happened in the pre-fix (Sept 14) runs that used native ScheduleWakeup/Monitor, and whether the post-fix wait guard has fired since.

`check-full` monitors fell from 30 on Sept 18 to 9, then 1, then 0 after the Sept 19 explicit-only change. Checking which providers are active now, since your complaint is current.

I have enough evidence and am starting the report now. First confirming the target filename is free.

Writing the report now.

Report written. Fixing a few wording details to match the exact numbers before registering it.

Registering the report as a durable artifact.

Artifact registered (`file:explicit:a45b3e221d06f59121470617`). Submitting the SASE final declaration.

Your guess is only partly right: confusion about headless mode was the main cause before Sept 15, but not since. What you're mostly seeing now is SASE's own `sase monitor start`, which kills the agent on purpose. It's being triggered at the wrong time and throwing away work that was already running.

I audited 1,193 agent runs from Sept 14–21, plus the 270 monitors and the recorded `sase tool run check` durations in that window.

**Headless confusion: real for Claude, now fixed there**
- On Sept 14, 10 of 67 Claude runs used Claude Code's own background tools (`run_in_background`, `ScheduleWakeup`, `Monitor`, `TaskOutput`). They then ended saying the task "will notify me automatically."
- Commit `bdda3bdf1` (Sept 15) fixed this. Since then, 0 of 269 Claude runs have used them.
- Two gaps remain:
  - `Monitor`, `CronCreate`, `RemoteTrigger` and `PushNotification` are still offered to headless Claude agents; only `ScheduleWakeup` is blocked.
  - The Claude headless instruction contradicts the monitor skill. One Claude agent concluded monitors can't work and ran its long jobs inline instead.
- Only Claude and Antigravity (`agy`) get any single-turn instruction or wait detection. Codex, Grok, Muse, Qwen and OpenCode get none.
- One genuine silent exit: `agy` phase agent `sase-14t.3` ended with "waiting for `sase doctor`," was recorded as `completed`, and its bead is still IN_PROGRESS 21 hours later.

**What's actually killing agents: the monitor handoff**
- It ended 190 runs (16% of all runs, and 49% of Grok runs).
- **Commands are long.**
  - `just check` takes a median of 4.5 min but p90 of 34–45 min, max 67–135 min.
  - `check-full` takes up to 4.6 hours.
  - Causes: host load of 46–50, and each workspace rebuilding the Rust extension. One `just test` took 17.5 min for 12 seconds of actual tests.
- **Every provider's tool call gives up well before that.** Grok moves commands to the background after about 15s, Muse after 300s, and Codex keeps polling (about 5,500 "still waiting" lines across 226 runs).
- **The guidance asks agents to guess.** It says to run `just check` inline but "hand it to a monitor whenever it is taking a long time." A monitor can only start a new command, not take over a running one. So agents start inline, cancel mid-run, and restart from zero.
  - Example: `sase-14n.14--plan` (Muse) cancelled a 61-minute-old check, handed it to a monitor, and the check started over.
  - 11 Muse runs killed in-flight commands this way, including `just install`.
- **Failed verification becomes a loop.** Fail, then a new agent makes a small fix, then a full re-verify under another monitor.
  - 23 agent families ran 3 or more monitors.
  - `sase-126.4` failed 14 times in a row over about 8 hours. `0mu` and `0nh` each spent about 10–15 hours looping.
- Making `check-full` explicit-only (Sept 19) already cut `check-full` monitors from 30 a day to 0.

**What I recommend:** let the tools decide when a wait becomes a handoff, and never throw away a run that's in progress. More "you are headless" prompting won't fix it; the Muse and Grok agents had read the monitor skill and still cancelled and restarted.
1. **Runs that survive the agent and can be joined.** `sase tool run` keeps running when the agent is killed. An identical request, including from a monitor, attaches to the running command instead of restarting it. This belongs in sase-core.
2. **An automatic handoff switch.** A `--handoff-after` option (default in the `verify` profile) turns a still-running command into a monitor that takes over the existing process. The cutoff is set per provider: late for Claude, which can block cheaply; early for Grok and Codex, which poll.
3. **Consistent headless handling for every provider.** Wait detection for Codex, Grok and Muse; a fix for the `agy` false `completed`; block the remaining Claude background tools; one instruction wording that agrees with the monitor skill.
4. **A limit on retry loops.** Re-run only the failed tests first, stop and ask you after 3 failed verification monitors, and set monitor timeouts from past run times.
5. **Faster verification (longer term).** A shared prebuilt Rust wheel per sase-core commit, and admission control for test runs.

Limits of the audit: it covers only this machine (athena); Muse handoffs are slightly undercounted; and whether Codex's heavy polling caused its usage-limit shutdowns is plausible but unproven.

The report is at `sase/repos/research/202609/headless_agent_early_exit_audit__cld.md`. It's registered as `research:202609/headless_agent_early_exit_audit__cld.md` (ref `file:explicit:a45b3e221d06f59121470617`), and its commit was submitted to the host.
