# Chat History - ace-run (research.3d.mus)

- **TIMESTAMP:** 2026-10-02 12:55:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3d.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124445.md`

## Prompt

%id(mus, clan=research.3d)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3d.cdx`, `research.3d.cld`, `research.3d.grk`, `research.3d.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Traversing through
the "current project" stack using the `<ctrl+n/p>` keymaps can be painfully slow in the
prompt input widget. Also, activating the prompt input widget using the `<space>` keymap
can be pretty slow sometimes too. It is very important that both of these operations are
very fast.

Can you do some research with the goal of helping me decide the best way to make these
keymaps work much faster? End your analysis with a recommended solution. 
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

Research complete. Report written to `sase/repos/research/202610/prompt_current_project_cycle_perf__mus.md` and registered as `research:202610/prompt_current_project_cycle_perf__mus.md` (artifact id `explicit:96610ea4b9f3551d3cc80296`).

Top finding: both slow keymaps share one root cause — every `ctrl+n/p` press and every `space` activation synchronously runs the uncached `load_launchable_vcs_xprompt_mru*()` chain (JSON read + full project/patch enumeration + per-entry spec-file pruning + a possible prune *write*) on the UI thread. Measured 0.5–5.3 s cold (import avalanche) and ~24 ms warm, already over the 16 ms key-to-paint budget at just 3 projects.

Recommended solution: cache the launchable-MRU snapshot keyed by change tokens with background refresh (prune-writes move off the keystroke path), warm the import closure once at startup/mount, and serve `space` prefill from the same cache — mount first, fill after if cold.

Declaration submitted (commit for `202610/prompt_current_project_cycle_perf__mus.md`).
