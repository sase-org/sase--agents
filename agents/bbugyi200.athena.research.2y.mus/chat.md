# Chat History - ace-run (research.2y.mus)

- **TIMESTAMP:** 2026-09-30 06:41:45 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.2y.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%id(mus, clan=research.2y)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.2y.cdx`, `research.2y.cld`, `research.2y.grk`, `research.2y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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

Report written and registered (`research:202609/prompt_history_machine_recordings__mus.md`, artifact `explicit:597eda47399a12834d3f30d4`).

Top finding: the screenshot's floods are expanded swarm-slot prompts written by `add_or_update_prompt(record_segments=True)` — one swarm submit stores N+1 rows — compounded by two more leaks: `%r:N` repeat records N machine slot rows and zero parent rows, and routine `sase run` subprocesses are stamped `typed` because only `SASE_AGENT` (not chop env) triggers `generated`. The existing origin column only feeds prediction; no read surface filters on it, and `PromptHistoryRecord` drops origin entirely.

Recommendation: record only the pre-expansion submitted text (one `typed` row), skip segment/slot/routine writes entirely, extend `_effective_prompt_origin` to chop env, hide `generated` on read surfaces by default, and ship a heuristic backfill since legacy flood rows carry no origin. The plan's core idea is sound, but as stated it misses the legacy-data problem and the single-slot expanded-text case.

Declaration submitted for `sdd:research` (commit of `202609/prompt_history_machine_recordings__mus.md`).
