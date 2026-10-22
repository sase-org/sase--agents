# Chat History - ace-run (research.2y.cld)

- **TIMESTAMP:** 2026-09-30 06:45:59 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2y.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%id(cld, clan=research.2y)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2y.cdx`, `research.2y.grk`, `research.2y.mus`, `research.2y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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

I'm mapping where prompt history gets written. There's already a new `origin: typed|generated` field (added yesterday in epic sase-1cj), so next I'll check how each launch surface sets it.

Now analyzing the live prompt-history shard to see which rows are machine-generated since origins started being recorded yesterday.

Origin tagging already exists at nearly every write site. Now I'm checking the remaining paths (repeat/alt fan-out, restart, TUI submit, routines) for rows that are wrongly labeled or missing.

Opening sase-core read-only to see how the prediction engine's `looks_generated` heuristic classifies machine prompts.

Nearly done with the investigation. Last check: whether a routine job script that shells out to `sase run` would be mislabeled as `typed`.

I have enough evidence. One quick byte-share measurement, then I'll write the report.

Writing the report now.

The report is written and registered. Last step is the SASE final declaration.

I wrote the report to `sase/repos/research/202609/prompt_history_human_requests_only__cld.md` and registered it as `research:202609/prompt_history_human_requests_only__cld.md` (artifact `explicit:5f1d79476a3d07a2ef8da8c8`). The host commits it after this turn.

**Is this a good idea?** Yes, and it's urgent. Your own history is mostly machine-generated:

| Shard | Machine-generated rows |
|---|---|
| 2607 | 55% |
| 2608 | 73% |
| 2609 | 80% |
| First page of the `Ctrl+K` history modal | 82 of 100 |

These rows are also risky to replay: loading an epic row and submitting it relaunches every phase with fixed agent names.

**Key findings:**
- **The screenshot row is neither a swarm nor a routine.** It's a `sase bead work` epic launch that an agent ran after your 06:02 "relaunch the epics" prompt. Each epic launch writes one row for the whole prompt plus one per phase, so 5–12 rows each. Your two proposed exclusions wouldn't remove it.
- **The classification already exists.** Yesterday's commit `eaa4aa4aa7` tags every history row as `typed` or `generated`, and almost every launch path already sets it correctly. Only next-word prediction uses the tag; the history modal, `sase prompt list`, word completion and placeholders ignore it.
- **The swarm rule is already mostly met.** Since May, launching a swarm records only the `#research_swarm` trigger. Member prompts get in through relaunches and one TUI path that swaps out a disabled provider.
- **Other leaks:**
  - A `%r:N` prompt is stored as N rewritten per-agent rows, and never as the text you typed.
  - A job script that shells out to `sase run` gets tagged `typed`.
  - A plugin that calls the launch API without saying where the prompt came from still gets recorded.

**Adjustments to your requirements:**
1. Replace "exclude swarms and routines" with one rule: record only text a human submitted (TUI, `sase run` or `sase prompt run` from a terminal, mobile), once per submission. The swarm and routine cases follow from it.
2. Record one row per request, using the text you typed: fix `%r:N`, the provider-swap path, and force-reuse (`%id(!name)`), which currently record rewritten prompts.
3. Relaunching an agent is not a new request unless you edit the prompt, and then only if the agent wasn't a swarm, epic or routine member.
4. Clean up the roughly 8,000 existing machine rows; a write-side fix alone leaves the modal noisy for months.
5. Don't stash failed machine launches either; the stash is meant for your own drafts.

**What I'd do instead:** decide at write time from where the prompt came from, not by hiding rows in the modal and not by pattern-matching prompt text. Hiding at read time would mean adding the tag to every reader, including the Rust filter, while the store keeps growing at about 4:1 noise.

**Recommended solution, in four phases:**
1. **Stop writing machine prompts.** Have the two history-write functions return early for `generated` rows. Also treat the routine job environment variables (`SASE_JOB_*`) like `SASE_AGENT`. Make launch callers that don't declare an origin default to `generated`, so new automation is never recorded by accident. This is about 15 lines plus tests and a docs update.
2. **Record exactly what you submitted** (the three fixes in adjustment 2).
3. **Apply the relaunch rule** in the TUI's edit-and-relaunch.
4. **One-time cleanup:** a new `sase prompt prune --generated` option that shows a dry run and makes a backup first. It would reuse sase-core's existing `looks_generated` check (it needs a Python binding plus a couple of extra markers it currently misses) and never touch `typed` rows.

Two open questions are in the report: whether a LaunchApproval prompt you edit before approving should count as typed, and whether gate follow-up and monitor commands that run `sase run` set an automation marker (I didn't verify that).
