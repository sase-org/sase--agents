# Chat History - ace-run (research.40.cld)

- **TIMESTAMP:** 2026-10-07 13:28:19 EDT
- **MODEL:** claude/opus
- **AGENT:** research.40.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_130213.md`

## Prompt

%id(cld, clan=research.40)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.40.cdx`, `research.40.grk`, `research.40.mus`, `research.40.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking that some of the builtin routines and/or jobs that exist currently
might be better suited as service procs. For example, wouldn't it be better if the
`wait_checks` job was instead a service proc that could wake up agents that are ready
sooner?

Can you do some research with the goal of recommending which jobs (if any) I should
migrate to service procs? Also, critique this plan in general. Is this a good idea?
Would you take a different approach? Make any adjustments to the requirements that you
think are justified but clearly call these out. End your analysis with a recommended
solution. 
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

I'm reading the scheduler (AXE) config and code to see how routines, jobs, fs triggers, and service procs work today.

Three subagent reports are back. Before writing, I'm checking their key claims against the code and the on-disk state myself.

I'm tallying how October's waiting agents were actually released, which shows how much `wait_checks` matters today.

I've confirmed that 883 of the 912 waiting markers belong to dead runners. Now I'm verifying two secondary claims: the hooks-lane trigger and the `pr_submitted_checks` cache.

Still verifying: `sase update` only restarts the scheduler proc, so a new long-lived daemon would keep running old code after an update. Checking the existing inotify watcher's platform support next.

I have enough evidence on the waits path. Last checks: the open duplicate-service-host bead and the memory footprint of a long-lived routine process, then I'll write the report.

Verification is done, and the main claims hold on athena. I'm checking two more line references, then writing the report.

The report is next. All the numbers in it come from my own measurements on athena today or from file:line checks in the repo.

The report is written. Now registering it as an artifact.

Registration succeeded. Now submitting the final declaration.

I wrote the report and registered it as a durable snapshot (`research:202610/jobs_vs_service_procs_wait_latency__cld.md`, ref `file:explicit:e3c6076cd7abd38832fced4c`). My recommendation is to move none of the builtin jobs to service procs for now, including `wait_checks`. Agents do wake slowly, but that's caused by three bugs in the `waits` routine, not by `wait_checks` being a job.

**What's actually slowing wake-ups (measured on athena today):**
- **The file trigger for `wait_checks` (and `bead_claim_checks`) can't see agents finish.** It watches the month folders under `ace-run/`, but runs live two levels deeper (`YYYYMM/DD/<run>/done.json`). So `wait_checks` only runs when its 120s backstop timer expires; I saw it fire about every 143s. The trigger test builds the wrong folder layout, which hides the bug.
- **Each `wait_checks` run takes about 30s, almost all of it on dead agents.** 883 of the 912 `waiting.json` files belong to runners that are no longer alive, and 880 of those are over a week old.
- **The `waits` routine cycles every ~25s, not 10s.** Each cycle waits for its slowest job (`bead_claim_checks` 33s, `wait_checks` 30s, `sidecar_auto_sync` 15–25s), and the log reports "Tick overrun" almost every cycle.
- **As a result, the waiting agent's own 60s fallback check releases about 80% of waits.** In October runner logs, 298 waits were released by that fallback and only about 70–95 through `ready.json`. That fallback also rereads every run folder in the project, once a minute, for each waiting agent.

**Why I wouldn't build a daemon:** the scheduler is already a service proc, and its routines are already long-running processes. What's missing is the ability to start a job as soon as a file changes. A separate service proc would give up a lot that jobs have now:
- per-run history and logs
- manual run and `--dry-run`
- per-run timeouts
- maintenance-mode pause
- automatically running new code after `sase update`, which only restarts the scheduler
- simple retry-next-cycle failure handling

The repo already shows these risks. A big Rust daemon project was built and then reverted in May. Moving Telegram long-polling from a job to a service proc in September silently dropped every duty that only the job's cycle performed.

**Recommended plan:**
- **Phase 0 (hours): measure.** Record how each wait was released and how long it took, and set a target (I suggest median ≤5s and 95th percentile ≤15s for agent waits).
- **Phase 1 (small): fix the waits routine.**
  - Point the trigger at `.ace_refresh_pulse`, which every `done.json` write already touches.
  - Skip waiters whose runner is dead.
  - Give `wait_checks` its own fast routine.
  - Once that works, slow the agent's own fallback check to every 5 minutes.
  - Expected: about 3–8s from dependency finish to release, versus roughly 20–35s today.
- **Phase 2 (medium; touches sase-core): event-wake for jobs.** The scheduler watches the files a job's trigger names (Linux inotify) and runs that job right away, keeping polling as the backup and on macOS. This also speeds up bead-sync and the hook-to-mentor-to-workflow pipeline, and every job keeps its history, timeouts and dry-run.
- **Phase 3: a separate `waits` service proc only if measurements still miss the target.**

**Rule for later candidates: daemons listen; jobs reconcile.** A service proc makes sense only when something has to hold a connection open, like the mobile gateway or the Telegram receiver. None of the 28 builtin jobs does. The one reasonable migration anywhere in the system is your user-configured `tg_outbound` job folding into `telegram_receiver`, and that's optional.

I requirements I changed are called out in the report (a latency target instead of "migrate jobs", measure first, keep a polling backup, new code must run after an update, must still work on macOS, bead waits in scope). I also found six follow-ups, including a minor cache bug in `pr_submitted_checks`. I didn't file them as beads so five researchers don't create duplicates; they're listed in §8 for the lead.

While grepping runner logs, the output included two lines from other agents' transcripts about this topic. I didn't open those logs or use them, and I note this in the report.
