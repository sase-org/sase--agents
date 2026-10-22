# Chat History - ace-run (research.2y.grk)

- **TIMESTAMP:** 2026-09-30 06:41:25 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.2y.grk
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%id(grk, clan=research.2y)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.2y.cdx`, `research.2y.cld`, `research.2y.mus`, `research.2y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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

I'll start by reading the research and SASE skills, then inspect the screenshot and how prompt history is stored today.

The screenshot lives under `~/tmp/screenshots`. Next I’ll inspect it and map how prompt history, xprompt swarms, and routines currently work.

The screenshot shows swarm-member and empty `+sase` rows crowding history. I’ll read the prompt-history, xprompt, and routine code next.

Origin already exists (`typed` vs `generated`). I’ll trace launch paths, swarm expansion, and routine launches next.

I have a clear picture of the write path and the screenshot clutter. Next I’ll write the independent report and register it as an artifact.

The idea is right. Prompt history should store the prompt a human submitted, and the screenshot clutter is generated launch text. The stated swarm-and-routine exclusions are too narrow.

The highlighted History row is a rendered `sase bead work` / epic-clan multi-prompt (`#bd/work_phase_bead`, `%clan(sase-1d5, tribe=epic, …)`), plus per-segment copies. A change that only skipped xprompt-swarm members and lumberjack chops would leave that flood in place.

The code already has the right taxonomy: `origin: typed | generated`. Next-word prediction drops generated rows. History still writes and shows them. The 06:07 `#research_swarm` invocation is already stored as the human request; the legacy CWD path does not re-record expanded members. Typed-admission unit dispatch, bead work, chops, plan follow-ups, and restarts still write `origin=generated`.

**Recommended solution**

- Stop persisting `origin=generated` at `add_or_update_prompt` (placeholders and segments included).
- Record each human submitted prompt once, including typed admission (`%if`/`%proc`) and `%r:N`, which currently miss or duplicate the source text.
- Keep user-authored `---` segments and short typed swarm triggers (`allow_short`).
- Default History / `sase prompt list` to typed rows; use Rust `looks_generated` only for legacy unlabeled rows; never hide `origin=typed`.
- Add an explicit `sase prompt prune --origin generated` for leftover shards.

Full write-up: `sase/repos/research/202609/prompt_history_record_human_requests_only__grk.md`  
Registered as `research:202609/prompt_history_record_human_requests_only__grk.md` (`file:explicit:4b9386436d748f764040c491`).
