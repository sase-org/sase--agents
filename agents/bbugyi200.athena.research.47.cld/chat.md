# Chat History - ace-run (research.47.cld)

- **TIMESTAMP:** 2026-10-09 13:40:28 EDT
- **MODEL:** claude/opus
- **AGENT:** research.47.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261009_130507.md`

## Prompt

%id(cld, clan=research.47)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.47.cdx`, `research.47.grk`, `research.47.mus`, `research.47.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

I'm building a list of real failure messages from this machine's agent logs, to work out which error patterns should trigger an automatic restart.

Checking what happens to agents that are waiting on a failed agent when it gets dismissed, since an automatic restart must not leave them stranded.

I've read the project rules on flags, completion, and the Rust boundary. Now I'm checking how background jobs are scheduled and how the existing drain notification is worded.

I have enough to write the report. Collecting exact line references first.

The journal shows 32 updates in four days (up to 16 on Oct 8), so agents run into code swaps all the time. Writing the report now.

Report written. Registering it as a durable artifact.

Registration succeeded. Now submitting the final declaration.

I wrote the report and registered it as `research:202610/agent_auto_restart_after_sase_code_swap__cld.md`; the commit has been declared and lands when this turn ends. My recommendation: build it, but as a backup to prevention, not as a literal "`,x` and resubmit".

**What happened today.** Four agents died this way. All four crashed inside `refresh_runner_code_after_wait()`, the code that is supposed to let an agent survive a sase update while it waits. It notices the code changed, then loads modules from the new code on disk before restarting itself onto that code. Its old in-memory version asked for `auto_launch_prefix`, which commit `9fd8a081f4` had just deleted. Running the restart first, before anything else, would have prevented all four. Current master still has this shape, so that fix should ship either way. All four were still waiting on dependencies, so no model work was lost.

**How big the problem is.** I checked all 905 failed agents on athena since July. 43 of them (about 4.8%) died because sase's code changed under them. `sase dev update` ran 32 times in the last four days. The global `sase` imports from live git checkouts (sase, its plugins and even the Rust core), so any long-running agent can hit this.

**Problems with the literal plan:**
- **`,x` is wrong for about half the cases.** 21 of the 43 died after the model had finished its work. A fresh relaunch would redo that work at full cost, strand the uncommitted changes in the old workspace, and could create duplicate commits.
- **An error message alone isn't enough evidence.** `cannot import name …` is also exactly what a real bug on master looks like. Each restart should also need independent proof that sase's code changed while that agent was running.
- **The restart can't run inside the crashing process,** because that process is the one with mismatched code. Today's crash site also never reaches the existing retry logic.

**Changes I'm proposing to your requirements** (all marked in the report):
- "Exactly once" becomes "at most once per agent and its replacements". A second failure gets reported, never retried.
- What sase does depends on when the agent died:
  - **Before the model ran:** your `,x` behaviour, always keeping the same name so agents waiting on it still find it.
  - **After the model ran:** resume in the original workspace with the chat continued.
  - **Unclear or risky cases:** ask you with a one-tap prompt instead of acting.
- Wait until the update has finished and the install checks out before restarting.
- Send one notification per update instead of one per agent.
- Never touch agents you killed, dismissed, or are editing.
- Keep a copy of the original error, since reusing the name deletes the failed run's files.

**Recommended design:**
- **Who restarts:** a separate, freshly started process. The dying agent wakes it through the existing `code_swap_guarded_exec.py`, which already waits for an in-flight update to finish. A scheduled job catches anything that slips through.
- **When it restarts:** only on a known error pattern plus proof the code moved during that agent's run: the update journal in `~/.sase/logs/dev_update.jsonl`, or a code version recorded at agent start. A durable record guarantees one attempt per agent.
- **Which patterns:** the report has the full list in four tiers with real examples and counts. It covers broken Python imports, Python/Rust version mismatches, and "written by a newer sase version" data errors. It also lists failures that should never trigger a restart.
- **What you see:**
  - In the Agents tab, an amber `RESTARTING ↻` instead of a red `FAILED`, and a ↻ note on the replacement explaining why.
  - One notification per update, such as "↻ Restarted 4 agents after sase update d7c4958 → 9fd8a08", whose report keeps updating with each agent's progress.
  - A single information-level toast instead of a pile of red ones.
- **Long term:** pin each process to a fixed copy of the code chosen when it starts. That stops sase's own code from changing under a running agent. Restarts would then only be needed for the rarer case of an old process reading data a newer one wrote.

**Questions for you:**
- Should resume-after-the-model-ran happen automatically in the first version, or go through a one-tap prompt until it has proven itself?
- Is it OK to always reuse the agent's name, even when its prompt didn't set one?
- Do you want the "fixed copy per process" install change? It's the only option that makes updating during runs safe by design rather than recovered after the fact.
