# Chat History - ace-run (research.1r.cld)

- **TIMESTAMP:** 2026-09-10 15:42:29 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1r.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260910_152511.md`

## Prompt

%id(cld, clan=research.1r) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1r.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I want to improve sase monitors (don't be afraid to get
creative or of big changes if they really lead to the best possible solution) and make
them more token efficient if possible. Can you do some research with the goal of helping
me decide the best way to implement this? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

I'll start by understanding the current sase monitor implementation.

Now I'll write the report.

Report written. Now registering it as a durable artifact snapshot.

Registration succeeded. Submitting the turn's final declaration.

Research complete.

**Report:** `sase/repos/research/202609/monitor_token_efficiency__b.md`
**Artifact:** `file:explicit:1a600c07aa815f3a01ea020b` (label `research:202609/monitor_token_efficiency__b.md`)

## What I found

I measured your actual chat corpus (`~/.sase/chats/202609`, 2,371 transcripts) rather than reasoning from code alone, restricting to files written after `a45669b26` landed so the numbers describe current behavior.

**Monitors are 17% of chats but 94% of all prompt bytes.** Since 2026-09-06 15:00: 340 monitor follow-ups consumed 40.1 MB of prompt; the other 1,693 chats consumed 2.7 MB. Median monitor prompt is 36 KB vs 1.07 KB for everything else.

**The cost is duplication, not command output.** Counting `# Monitored command finished` per prompt gives a perfect geometric series — 1, 2, 4, 8, 16, 23, 32 breakdowns — because each hop down a monitor chain doubles the replayed evidence. One real 1.28 MB prompt carries **32 breakdowns for only 6 distinct monitors**; the oldest is replayed sixteen times. 34% of monitor prompt bytes are byte-identical duplicate blobs. 3% of follow-ups start with a prompt that alone exceeds a 200K-token window.

**Root cause, in two lines of code.** `run_agent_exec_finalize.py:177` persists the *fully expanded* prompt (with injected fork history baked in) into `## Prompt`; `load_chat_for_resume` then replays that text *and* re-derives the same ancestors by following `#fork` refs. One hop, two copies. `write_chat_history` already has an unused `previous_history=` parameter built for exactly this.

**Separately, the 200-line tail is a bad selector.** Across 134 `FAILED just check*` monitors it carried the actual failing-test detail only 25% of the time; 46% contained nothing but `error: recipe ... failed`. You're paying ~9.4 KB per follow-up for a pointer.

## Recommendation

Phase 1 — unbake the history and make command evidence a transient region that replays as one line. Simulated against the real corpus: **40.27 MB → 5.33 MB (-87%)**, worst case -98%, ~8.7M tokens per 4 days on this machine. Both hooks already exist; no new subsystem.

Phase 2 — structured digests (`--next-digest`) instead of a positional tail, outcome-conditional by default, plus `--next-on-success`/`--next-on-failure`. Smaller *and* more useful.

Phase 3 — trim the `/sase_monitor` skill (it still teaches deprecated `--command` as canonical, at ~1.7K tokens a call), then flag-gate a provider session-resume experiment. I deliberately ranked resume last: it's a real quality and latency win but an *uncertain* token win, since a resumed session re-sends tool results the fork omits and can lose on a cold cache.

I explicitly rejected LLM-summarizing the transcript (solves the symptom; 90% of the bytes are exact duplicates that can be deleted for free) and lowering the tail bounds as a primary fix (saves 2%, makes the signal problem worse).
